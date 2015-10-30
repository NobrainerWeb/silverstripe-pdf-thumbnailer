silverstripe-pdf-thumbnailer
============================

PDF thumbnail generator module for SilverStripe

## Overview

Generates thumbnail images for PDF files using ImageMagick.

## Requirements

SilverStripe 3.1

## Installation

Extract the archive to your project root, then run /dev/build?flush=1.

Make sure you have the ImageMagick binary 'convert' installed on your target server.

If convert is installed somewhere other than /usr/bin/convert, you will need to set where it is in your config.yml file:
```
PdfThumbnailerExtension:
  convert_path: '/usr/local/bin/convert'
```

## Usage

In your .ss templates, use the following to output a fullsize image of the first page:

    <% with File %>$Thumbnail<% end_with %>

If the file can't be thumbnailed, nothing will be output.  Otherwise you will get an IMG tag.

You can use this with any other normal image processing, eg:

    <% with File.Thumbnail %>$SetWidth(64)<% end_with %>

You can also output any page you wish by passing the page number to the Thumbnail function:

    <% with File %>$Thumbnail(6)<% end_with %>
    <% with File.Thumbnail(3) %>$SetWidth(64)<% end_with %>

