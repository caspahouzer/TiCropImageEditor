# Titanium module for PEPhotoCropImage

This is my first attempt to build a native module for Titanium.
The module wraps the excellent library developed by kishikawa katsumi,

that you can find here:

https://github.com/kishikawakatsumi/PEPhotoCropEditor

that allows to crop and resize images, in a similar way the native iOS Photo Gallery.app does.

Using the module is quite simple:

Import the module in your code with:
```js
var TiCropImageEditor = require('it.etnatraining.TiCIE');
```

then create an image editor instance with:

```js
var imageEditor = TiCropImageEditor.createImageEditor();
```

and open the image editor:

```js
imageEditor.open(e.media);
```

The only accepted parameter is a `Ti.Blob` that represent the image you want to edit.

Currently the resized/rotated image is written to a file in the bundle Documents directory.
To retrieve the name of the file, you need to listen for the event "done":

```js
imageEditor.addEventListener("done", function(e) {
    alert(e.filename);
});
```
The filename is found in the filename property of the event object.

Notes
=====

- This is a very early/alpha release. I don't suggest to use it in production right now, cause I don't take care carefully of memory management.
- This module is iOS only

https://jira.appcelerator.org/browse/TIMOB-12558


