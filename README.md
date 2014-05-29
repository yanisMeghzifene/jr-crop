jr-crop
======

A simple ionic plugin to crop your images, inspired by whatsapp and telegram.
* Specifiy width and height of target
* Doesn't actually scale the image, only returns a cropped version. Since the quality of images while scaling is inconsistent it's up to the developper to implement this, preferably on the server.
* Returns a canvas element with the new cropped image.

## Simple enough, let's get started.
Include jr-crop where you'd like to use it.
```
.controller('MyController', function($jrCrop) {
```

Call the crop function to open a new modal where the user can crop this image. Pass in the image url and targetsize. The function will return a promise that resolves when the user is done or fails when the user cancels.
```
$jrCrop.crop({
    url: url,
    width: 200,
    height: 200
}).then(function(canvas) {
    // success!
    var image = canvas.toDataURL();
}, function() {
    // User canceled or couldn't load image.
});

## Examples please!!
I got ya. Run `bower install` in the root and `node app.js` from the examples folder. Visit `localhost:8080/examples`. Great now you can visit this from your phone too. It works best when packaged in cordova, as how you should use ionic anyway.