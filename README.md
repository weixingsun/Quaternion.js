# Quaternion.js - ℍ in JavaScript

[![NPM Package](https://img.shields.io/npm/v/quaternion.svg?style=flat)](https://npmjs.org/package/quaternion "View this project on npm")
[![Build Status](https://travis-ci.org/infusion/Quaternion.js.svg?branch=master)](https://travis-ci.org/infusion/Quaternion.js)
[![MIT license](http://img.shields.io/badge/license-MIT-brightgreen.svg)](http://opensource.org/licenses/MIT)



Example with HTML5 Device Orientation
---
In order to create a HTML element, which always rotates in 3D with your mobile device, all you need is the following snippet. Look at the examples folder for a complete version.

```
var q = new Quaternion;
var rad = Math.PI / 180;
window.addEventListener("deviceorientation", function(ev) {

  // Update the rotation object
  q.setFromEuler(ev.alpha * rad, ev.beta * rad, ev.gamma * rad, 'ZXY');

  // Set the CSS style to the element you want to rotate
  elm.style.transform = "matrix3d(" + q.conjugate().toMatrix4() + ")";

}, true);
```



Installation
===
Installing Quaternion.js is as easy as cloning this repo or use one of the following commands:

```
bower install quaternion
```
or

```
npm install quaternion
```

Using Quaternion.js with the browser
===
    <script src="quaternion.js"></script>
    <script>
        console.log(Quaternion("1 + 2i - 3j + 4k"));
    </script>


Using Quaternion.js with require.js
===
    <script src="require.js"></script>
    <script>
    requirejs(['quaternion.js'],
    function(Quaternion) {
        console.log(Quaternion("1 + 2i - 3j + 4k"));
    });
    </script>

Coding Style
===
As every library I publish, Quaternion.js is also built to be as small as possible after compressing it with Google Closure Compiler in advanced mode. Thus the coding style orientates a little on maxing-out the compression rate. Please make sure you keep this style if you plan to extend the library.

Testing
===
If you plan to enhance the library, make sure you add test cases and all the previous tests are passing. You can test the library with

```
npm test
```


Copyright and licensing
===
Copyright (c) 2016, Robert Eisele (robert@xarg.org)
Dual licensed under the MIT or GPL Version 2 licenses.
