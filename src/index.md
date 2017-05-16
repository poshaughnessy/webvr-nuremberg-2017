title: WebVR - Getting started...
output: public/index.html
theme: peter-theme
controls: false

-- bg-fade-grey intro

# WebVR
## Getting started with Virtual Reality for the web

<div class="contact">
  <p>Peter O'Shaughnessy</p>
  <p>[@poshaughnessy](https://twitter.com/poshaughnessy)</p>
  <p>[@samsunginternet](https://twitter.com/samsunginternet)</p>
</div>

-- img-with-caption

![Samsung Internet logo](images/logo_Light_Font.png)

[samsunginter.net/about](https://samsunginter.net/about)

-- virtuality

-- white

![VR headsets](images/vr-headsets.jpg)


-- valign-top cliff

## Presence

<div class="credit">[Fotolia](http://www.fotolia.com/)</div>


-- valign-bottom grandma

<blockquote>&ldquo;I've made a lot of applications & nothing I ever created was ever going to make someone laugh, cry, recoil or scream like VR can.&rdquo;</blockquote>

<div class="caption">Josh Carpenter</div>

<div class="credit">[Paul Rivot](https://www.youtube.com/watch?v=pAC5SeNH8jw&feature=youtu.be)</div>

-- world-wide-web bg-fade

## “The best way to reach the widest number of customers in VR will be via the web.”

<div class="caption">Brandon Jones</div>

<div class="credit">[frankieleon](https://www.flickr.com/photos/armydre2008/6012029995)</div>

-- white

![WebVR](images/webvr-logo-square.png)

-- metaverse valign-bottom extra-vignette-2

[metaverse.samsunginter.net](https://metaverse.samsunginter.net/)

--

## WebVR provides...

* Headset discovery
* Full-screen headset display
* Sensor integration, e.g. orientation
* Rendering for different hardware

-- 

### Stereoscopic

<img src="images/oculus-stereo-normal.jpg" alt="Stereoscopic" style="max-width:80%; max-height: 70vh"/>

-- 

### Browser handles distortion

<img src="images/oculus-stereo-distortion.jpg" alt="Distortion" style="max-width:80%; max-height: 70vh"/>

-- browser-support

### Browsers

![Chrome for Android](images/chrome-android.png) ![Chromium](images/chromium.png) ![Firefox Nightly](images/firefox-nightly.png) ![Servo](images/servo.png) ![Samsung Internet](images/sbrowser5.0.png) ![Edge](images/edge.png) ![Carmel](images/carmel.png) 

[webvr.rocks](https://webvr.rocks/)


-- webvr-info valign-bottom

<div class="credit">[webvr.info](https://webvr.info/)</div>

-- 

![Requirements](images/webvr-requirements.png)


-- 

## WebVR API

### Version "1.1" - [bit.ly/webvr-update-sep-2016](http://blog.tojicode.com/2016/09/update-on-webvr-spec-chrome-and-https.html)

-- 

```javascript
// Get list of available headsets
navigator.getVRDisplays();

// Request fullscreen on headset
VRDisplay.requestPresent({ source: myCanvas })
```

-- 

```javascript
// Like normal rAF but could be 90hz or more 
VRDisplay.requestAnimationFrame();

// Render what's on the source canvas
VRDisplay.submitFrame();
```


-- 

```javascript
/**
 * Get eye offset & rendering dimensions to help us
 * construct a stereoscopic scene for the user.
 */ 
VRDisplay.getEyeParameters(VREye);

/**
 * Get view & projection matrices for current frame
 * & VRPose with pos, orientation, accel & velocity.
 */
 VRDisplay.getFrameData();

```


-- 

![WebGL](images/webgl-logo.png)


-- 

## three.js

![threejs.org](images/threejs_org.png)

<p class="caption"><a href="https://threejs.org/">threejs.org</a></p>


-- 

### Let's make a spinning cube

```javascript
var renderer = new THREE.WebGLRenderer();

renderer.setSize( width, height );

document.body.appendChild( renderer.domElement );
```


-- 

```javascript
var scene = new THREE.Scene();

var camera = new THREE.PerspectiveCamera(
  45,             // Field of view angle
  width / height, // Aspect ratio
  1,              // zNear
  1000            // zFar
);

camera.position.z = 100;

scene.add( camera );
```


-- 

```javascript
var cube = new THREE.Mesh(
  new THREE.BoxGeometry( 50, 50, 50 ), // w, h, d
  new THREE.MeshBasicMaterial( {color: 0xFF0000} );
);

scene.add( cube );
```


-- 

```javascript
function animate() {
  cube.rotation.y += 0.1;
  renderer.render( scene, camera );
  requestAnimationFrame( animate );
}

animate();
```

<p style="margin-top: 1em">[Here's one I made earlier](demos/threejs-spinning-cube/index.html)</p>

-- 

```javascript
var controls = new THREE.VRControls( camera );
var effect = new THREE.VREffect( renderer );

...

controls.update();
effect.render( scene, camera );
```


-- 

<img src="images/sbrowser-cubes1.jpg" alt="WebVR cubes on Samsung Internet" style="max-height:calc(100vh - 5em)"/>

[threejs.org/examples/webvr_cubes.html](https://threejs.org/examples/webvr_cubes.html)


-- webvr-cubes


-- aframe valign-top

## A-Frame

<!-- Remember to say it includes the polyfill for Cardboard -->


-- 

```html
<script src="aframe.js"></script>
```


-- 

```html
<a-scene>
  <a-sphere position="0 1.25 -1" radius="1.25" 
            color="#EF2D5E"></a-sphere>
  <a-box position="-1 0.5 1" rotation="0 45 0" 
         color="#4CC3D9"></a-box>
  <a-cylinder position="1 0.75 1" radius="0.5" 
              color="#FFC65D"></a-cylinder>
  <a-plane rotation="-90 0 0" width="4" height="4" 
            color="#7BC8A4"></a-plane>
  <a-sky color="#ECECEC"></a-sky>
</a-scene>
```


-- iframe

<iframe src="demos/aframe-basic/index.html" scrolling="no" width="100%" height="100%"></iframe>


-- llama-carousel valign-top

### Let's make a Flickr carousel


-- 

```html
<script src="aframe-layout-component.min.js"></script>

...

<a-entity id="imageContainer" 
          layout="type: circle; radius: 3"></a-entity>
```

-- 

```html
<script src="aframe-look-at-component.min.js"></script>
```

```javascript
function generateImage(id, src) {

  var imageEl = document.createElement('a-image');
  imageEl.setAttribute('src', src);
  imageEl.setAttribute('width', 1.25);
  imageEl.setAttribute('height', 1);
  imageEl.setAttribute('look-at', '0 0 0');

  imageContainer.appendChild(imageEl);

}
```


-- 

```html
<a-entity camera look-controls>
  <a-cursor></a-cursor>
</a-entity>
```


-- 

### Pre-canned animations

```html
<a-animation begin="click" 
             attribute="rotation" 
             to="0 360 0" 
             dur="1000" 
             fill="forwards"></a-animation>
```
<p class="caption">Just place inside an element</p>


-- 

### Or take control with Tween.js

```javascript
new AFRAME.TWEEN.Tween(el.object3D.rotation)
     .to({y: targetRotation}, 1000) // 1 second
     .start();
```     

-- sky-gawthrop

```html
<a-assets id="assets">
  <img id="mountainSky" src="images/sky_by_gawthrop.jpg"/>
</a-assets>
<a-sky src="#mountainSky"/>
```


-- iframe

<iframe src="demos/aframe-flickr-carousel/index.html" scrolling="no" width="100%" height="100%"></iframe>

--

## Examples

-- aframe-racer valign-bottom extra-vignette-1

[samsunginter.net/a-frame-demos/racer/](https://samsunginter.net/a-frame-demos/racer/)

-- pwacman valign-bottom extra-vignette-1

[samsunginter.net/pwacman](https://samsunginter.net/pwacman)

-- bubble valign-bottom extra-vignette-2

[samsunginter.net/bubble/](https://samsunginter.net/bubble/)

-- bubble-hollywood valign-bottom extra-vignette-2

[bit.ly/hollywood-bubble](http://bit.ly/hollywood-bubble)

-- word-drop valign-bottom extra-vignette-1

[samsunginter.net/word-drop/](https://samsunginter.net/word-drop/)

-- within valign-bottom extra-vignette-2

[vr.with.in](https://vr.with.in)

-- playcanvas-lab valign-bottom extra-vignette-1

[webvr.playcanvas.com](https://webvr.playcanvas.com)

-- pva bg-fade fade-less

# Progressive VR Apps

<div class="credit">[Victuallers](https://commons.wikimedia.org/wiki/File:Pva_wood_glue.jpg)</div>

-- img-with-header

### "Continuous browsing experiences"

![Continuous browsing experiences](images/continuous-browsing-experience.png)

-- img-with-header

### Responsive Design

![Responsive design](images/responsive-design.png)

*Assume small screen.*

*If > x pixels, apply desktop styles.*

-- img-with-header

### Responsive Experience

![Responsive experiences](images/responsive-experiences.png)

*Assume no VR headset.*

*If WebVR/polyfill & user taps button, start VR experience.*

-- img-with-header

### Responsive Fidelity

![Responsive fidelity](images/responsive-fidelity.png)

*Assume low-powered.* 

*If smooth frame rate, download higher-res assets.*

-- img-with-caption

![PlayCanvas Man-O-War](images/playcanvas-man-o-war.jpg)

[bit.ly/playcanvas-gun-project](http://bit.ly/playcanvas-gun-project)

-- img-with-caption gamepad-support

![Gamepad API support](images/gamepad-support.png)

[bit.ly/beta-gamepad-support](bit.ly/beta-gamepad-support)

-- controller valign-bottom

[samsung.com/global/galaxy/gear-vr/#controller](http://www.samsung.com/global/galaxy/gear-vr/#controller)

-- 

## Where next?

* Touchpad / controllers
* Physics / gaming engines
* Web Audio

-- valign-top another-world

## From web sites to web *worlds*

-- earth-rising valign-top

### What worlds will you create?

-- bg-fade-less-grey thanks valign-bottom

# Thanks!

<div class="social">
  <h3 class="twitter">[@poshaughnessy](https://twitter.com/poshaughnessy)</h3>
  <h3 class="twitter">[@samsunginternet](https://twitter.com/samsunginternet)</h3>
  <h3 class="github">[github.com/samsunginternet](https://github.com/SamsungInternet/)</h3>
</div>


