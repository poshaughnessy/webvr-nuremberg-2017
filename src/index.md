title: WebVR: Getting started...
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

-- align-top img-with-caption

![Samsung Internet icon on homescreen](images/samsung-internet-beta-phone-blur.png)

[Samsung Internet for Android](http://bit.ly/samsung-internet-open-beta)

-- img-with-caption

![Samsung Internet for Gear VR launch](images/gear-vr-browser-launch2.jpg)

[Samsung Internet for Gear VR launched, Dec 2015](https://news.samsung.com/global/samsung-launches-optimized-web-browser-for-gear-vr)

--

<video controls>
  <source src="videos/si4gvr-meetup.mp4" type="video/mp4">
  <source src="videos/si4gvr-meetup.webm" type="video/webm">
</video>

-- img-with-caption

![Samsung Internet for Gear VR WebVR support](images/gear-vr-webvr-support.jpg)

[WebVR support added, Apr 2016](https://www.slashgear.com/samsung-internet-browser-for-gear-vr-now-supports-webvr-04434526/)

<!-- NB. Samsung Internet for Gear VR - WebVR not enabled by default but prompts you to enable it -->

-- 

### “The best way to reach the widest number of customers in VR will be via the web.”

<div class="caption">Brandon Jones, Google</div>

-- browser-support

![Chrome for Android](images/chrome-android.png) ![Chromium](images/chromium.png) ![Firefox Nightly](images/firefox-nightly.png) ![Servo](images/servo.png) ![Samsung Internet](images/sbrowser5.0.png) ![Edge](images/edge.png) ![Carmel](images/carmel.png) 

[webvr.rocks](https://webvr.rocks/)

--

# Examples

-- pwacman valign-bottom extra-vignette-1

[samsunginter.net/pwacman](https://samsunginter.net/pwacman)

-- aframe-racer valign-bottom extra-vignette-1

[samsunginter.net/a-frame-demos/racer/](https://samsunginter.net/a-frame-demos/racer/)

-- bubble valign-bottom extra-vignette-2

[samsunginter.net/bubble/](https://samsunginter.net/bubble/)

-- bubble-hollywood valign-bottom extra-vignette-2

[bit.ly/hollywood-bubble](http://bit.ly/hollywood-bubble)

-- word-drop valign-bottom extra-vignette-1

[samsunginter.net/word-drop/](https://samsunginter.net/word-drop/)

-- metaverse-audience valign-bottom extra-vignette-2

[metaverse.samsunginter.net](https://metaverse.samsunginter.net/)

-- within valign-bottom extra-vignette-2

[vr.with.in](https://vr.with.in)

-- playcanvas-lab valign-bottom extra-vignette-1

[webvr.playcanvas.com](https://webvr.playcanvas.com)

-- pva bg-fade-less

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

-- video-360

![360 video](images/360-video.png)

```
<video controls src="360-timelapse.mp4" 
       type="video/mp4; dimension=360;"></video>
```

[samsunginter.net/docs/video-360](https://samsunginter.net/docs/video-360)

-- iframe

<iframe width="100%" height="90%" style="margin-top:5vh" src="https://www.youtube.com/embed/9NefsqY3uGw" frameborder="0" allowfullscreen></iframe>

-- 

```javascript
window.SamsungChangeSky({ 
  sphere: 'http://site.com/blue-sky.jpg' 
});
```
[samsunginter.net/docs/skybox](https://samsunginter.net/docs/skybox)

-- img-with-caption gamepad-support

![Gamepad API support](images/gamepad-support.png)

[bit.ly/beta-gamepad-support](bit.ly/beta-gamepad-support)

-- controller valign-bottom

[samsung.com/global/galaxy/gear-vr/#controller](http://www.samsung.com/global/galaxy/gear-vr/#controller)


-- bg-fade-less-grey thanks valign-bottom

# Thanks!

<div class="social">
  <h3 class="twitter">[@samsunginternet](https://twitter.com/samsunginternet)</h3>
  <h3 class="github">[github.com/samsunginternet](https://github.com/SamsungInternet/)</h3>
</div>
