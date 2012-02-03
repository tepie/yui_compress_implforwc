Example YUI Compressor Implementation for Websphere Commerce
=============

This is an example YUI compressor implementation for Websphere Commerce, however the implementation
is very basic and can be used anywhere. 

* http://developer.yahoo.com/yui/compressor/

The Details
------------

### ant.properties

You will need your own ant properties. This implementation expects:

* `prop.js.src.dir=` - The path to your source directory containing the javascript
* `prop.jar.yui_compress=yuicompressor-2.4.8pre.jar` - The YUI compression library

### How it works

The source directory given will be looped, each file will be minified. Each file will be given name <basename>-min.js.

### Example JSTLEnvironmentSetup.jspf

There is an included JSTLEnvironmentSetup.jspf that demonstrates how you can pass a URL parameter
to enable usage of the minified scripts during development. 

### Comments from JSTLEnvironmentSetup

* Example page include:

`<script language="javascript" src="<c:out value="${jsSearchURI}"/>" ></script>`

* Example URL Request with minify (value can be whatever):

https://localhost/webapp/wcs/stores/servlet/GenericPageView?minify=true&catalogId=100&langId=-1&storeId=100

Installation
-----------

You will need to ensure you have the ant-contrib libraries installed in your ant lib directory. Otherwise, 
you can just put this project in your eclipse workspace, or just checkout to the filesystem and run with ant. 

### Ant Targets

* `clean.js.loop` - Will delete the min files in the source directory
* `compress.js.loop` - Will minify all the files in the source directory