# burp-decompressor
An extension for BurpSuite used to access and modify compressed HTTP payloads without changing the content-encoding.

## Why this extension?
Often, HTTP traffic is compressed by the server before it is sent to the client in order to reduce network load.
Typically used algorithms are gzip or deflate. By default, BurpSuite will decompress all intercepted data in the body 
of HTTP messages in order to display plain text payloads in the different tabs and make stuff searchable. However, the
content is not recompressed back before it is sent to the browser. Usually, this isn't a problem.

In cases where the traffic is intended for other types of client instead of a browser, e.g. a fat/rich client using 
RMI over HTTP, the used content-encoding may sometimes be fixed and changing it will result in an error.

## What is it?
When using this extension, you will be able to access and modify compressed HTTP content in requests and responses
within a new tab in BurpSuite. The tab will appear as soon as compressed data is detected in a message body. For this,
you need to disable automatic unpacking of data by BurpSuite.

## How to disable automatic content decompression in BurpSuite?
In BurpSuite, open the Proxy tab, then the Options tab. Scroll to the bottom of the pane, under the title "Miscellaneous",
untick both "Unpack gzip / deflate in requests" and "Unpack gzip / deflate in responses".


## Acknowledgements
This is my first BurpSuite extension, highly inspired by https://github.com/federicodotta/BurpJDSer-ng-edited
