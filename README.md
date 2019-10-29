# Video Doorbell, Lab 7

*A lab report by John Q. Student*

### In This Report

1. Upload a video of your version of the camera lab to your lab Github repository
1. As usual, update your class Hub repository to add your [forked IDD-Fa18-Lab7](/FAR-Lab/IDD-Fa18-Lab7) repository.
1. Answer the questions in-line below on your README.md.

## Part A. HelloYou from the Raspberry Pi

**a. Link to a video of your HelloYou sketch running.**



## Part B. Web Camera

**a. Compare `helloYou/server.js` and `IDD-Fa18-Lab7/pictureServer.js`. What elements had to be added or changed to enable the web camera? (Hint: It might be good to know that there is a UNIX command called `diff` that compares files.)**

Had to implement NodeWebcam and include webcam setup

```
< //---------------------- WEBAPP SERVER SETUP ---------------------------------//
---
> const SerialPort = require('serialport')
> const Readline = require('@serialport/parser-readline')
34c11
< app.use(express.static('public')); // find pages in public directory
---
> app.use(express.static('public'));	// find pages in public directory
36,40c13,17
< // check to make sure that the user provides the serial port for the Arduino
< // when running the server
< if (!process.argv[2]) {
<   console.error('Usage: node ' + process.argv[1] + ' SERIAL_PORT');
<   process.exit(1);
---
> // check to make sure that the user calls the serial port for the arduino when
> // running the server
> if(!process.argv[2]) {
>     console.error('Usage: node '+process.argv[1]+' SERIAL_PORT');
>     process.exit(1);
43,77c20,21
< // start the server and say what port it is on
< http.listen(serverPort, function() {
<   console.log('listening on *:%s', serverPort);
< });
< //----------------------------------------------------------------------------//
< 
< //--Additions:
< //----------------------------WEBCAM SETUP------------------------------------//
< //Default options
< var opts = { //These Options define how the webcam is operated.
<     //Picture related
<     width: 1280, //size
<     height: 720,
<     quality: 100,
<     //Delay to take shot
<     delay: 0,
<     //Save shots in memory
<     saveShots: true,
<     // [jpeg, png] support varies
<     // Webcam.OutputTypes
<     output: "jpeg",
<     //Which camera to use
<     //Use Webcam.list() for results
<     //false for default device
<     device: false,
<     // [location, buffer, base64]
<     // Webcam.CallbackReturnTypes
<     callbackReturn: "location",
<     //Logging
<     verbose: false
< };
< var Webcam = NodeWebcam.create( opts ); //starting up the webcam
< //----------------------------------------------------------------------------//
```

[Differences](https://github.com/JwayYih/IDD-Fa19-Lab7/blob/master/diff.txt)

**b. Include a video of your working video doorbell**

[Working Doorbell](https://photos.app.goo.gl/WrmqcH1EJ6b2Djah9)

## Part C. Make it your own

**a. Find, install, and try out a node-based library and try to incorporate into your lab. Document your successes and failures (totally okay!) for your writeup. This will help others in class figure out cool new tools and capabilities.**

Used the [image-js](https://www.npmjs.com/package/image-js) package to manipulate images like resizing, cropping, grayscale, and color inversion.  Couldn't get it still unsure why.

**b. Upload a video of your working modified project**
