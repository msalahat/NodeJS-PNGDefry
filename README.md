node-pngdefry
==============
This is a nodejs wrapper for pngdefry command line tool that reverses the optimisation XCode does on png images included into iPA files to make the images readable by the browser.

### Why you may need it ?

If you want for any reason to extract App Icons (PNG images ) out of iPA files ( iOS Apps ) you will need this ; because you gonna find that those extracted PNG images are not readable by the browser . 

Apple uses [PNGCursh](http://pmt.sourceforge.net/pngcrush/) open source library to crush png images inside iPA files , to reverse this process back you need to do it throw pngdefy lib , 

### Platforms supported:

+ OSX (Drawin) : Must have built tools ( config , make ) installed.
+ Linux.



### Installation

[![NPM](https://nodei.co/npm/node-pngdefry.png)](https://nodei.co/npm/node-pngdefry/)

### Usage

```javascript
var PNGDDefry = require("node-pngdefry");
var source_image_file = __dirname + "/AppIcon57x57.png";
var destination_direcotry = __dirname + "/output";
var suffix = null;
var png_converter = new PNGDDefry();
png_converter.convert(source_image_file, destination_direcotry, null, function (err, output_image_path) {
    console.log(err);
    console.log(output_image_path);
});
```

+ source_image_file : the source for the png image to be deferd by the library.
+ destination_directory :  the destination directory where the result image need to be saved , by default it is saved by the original image name.
+ suffix : in case you want to save it in the same original image directory , you need to may use this argumant to add a suffix to the saved image name.

### Test

A test script is added under tests directory :
+ First open the image under /tests directory by the browser other than safari , it will not be displayed.

+ Run this commands inside the module root directory

```javascript
npm install
npm test 
```

+ If you have successfully installed the package ,the test should pass and   new image with the same name should be created under tests/output directory .

+ Open the image with your browser it should be displayed.

