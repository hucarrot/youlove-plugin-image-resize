
# Image Resizer plugin for Cordova 5.0+ #

This plugin resizes images natively using the cordova architecture.

## Adding the Plugin to your project ##

The plugin conforms to the Cordova plugin specification, it can be installed
using the Cordova command line interface.

```
cordova plugin add https://github.com/hucarrot/youlove-plugin-image-resize.git
```

## Using the plugin ##

The plugin creates the object `window.imageResize`. `window.plugins.imageResize` still works for older versions.

To use, call one of the following, available methods:

```javascript
   window.imageResize.resizeImage(successCallBack, failCallBack, imageData, width, height, options);
   window.imageResize.getImageSize(successCallBack, failCallBack, imageData, options);
   window.imageResize.storeImage(successCallBack, failCallBack, imageData, options);
```

For Example:
```javascript
window.imageResize.resizeImage(
   function(data) { 
     var image = document.getElementById('myImage');
     image.src = "data:image/jpeg;base64," + data.imageData; 
   }, function (error) {
     console.log("Error : \r\n" + error);
   }, imageDataInBase64, 0.5, 0.5, {
      resizeType: imageResize.RESIZE_TYPE_FACTOR,
      imageDataType: imageResize.IMAGE_DATA_TYPE_BASE64,
      format: imageResize.FORMAT_JPG
   }
);
```