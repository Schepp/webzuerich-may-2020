<h1 class="boom">6.</h1>
---
## Animated image formats

<img src="images/judge-dread-cinemagraph.gif" class="comic-border">
---
Animated GIFs have your back! 

<pre><code class="liveCoding xml" data-livecoding-id="format-agif" contenteditable>&lt;img src="images/explosion/explosion.gif"&gt;</code></pre>

<div id="format-agif"></div>
---
But at the same time they are pretty shitty... 💩

<ul>
  <li>⚠ Only 256 colors supported</li>
  <li>⚠ Only 1 bit of transparency supported (just on / off)</li>
  <li>❌ Huge file sizes</li>
  
</ul>
---
How about using Animated PNG instead? 

<pre><code class="liveCoding xml" data-livecoding-id="format-apng" contenteditable>&lt;img src="images/explosion/explosion.png"&gt;</code></pre>

<div id="format-apng"></div>
---
APNG is supported in every modern browser!

<ul>
  <li>✅ 24 bit of colors supported!</li>
  <li>✅ 8 bit of transparency supported!</li>
  <li>❌❌ Even more humongous file sizes... 💩 (4x GIF)</li>
  
</ul>
---
Motion-JPEG! Old, but gold.

<pre><code class="xml">&lt;img src="http://localhost/
imagery-on-the-web/explosion.mjpeg"&gt;</code></pre>

<div id="format-mjpeg" class="comic-border"><img src="http://localhost/imagery-on-the-web/explosion.mjpeg"></div>
---
Motion-JPEG is supported in every browser!

<ul>
  <li>✅ 24 bit of colors supported!</li>
  <li>❌ No transparency</li>
  <li>⚠ Okayish file sizes... (a little smaller than GIF)</li>
  <li>❌ Needs to be streamed as multipart JPEG-sequence from server 💩</li>
  
</ul>
---
Woah, WebP can be animated, too!?!?

<pre><code class="liveCoding xml" data-livecoding-id="format-webp" contenteditable>&lt;img src="images/explosion/explosion.webp"&gt;</code></pre>

<div id="format-webp"></div>
---
WebP is soon to be supported in almost every browser!

<ul>
  <li>✅ 24 bit of colors supported!</li>
  <li>✅ 8 bit of transparency supported!</li>
  <li>⚠ Okayish file sizes... (a little smaller than GIF)</li>
  <li>❌ Not supported in Safari 💩</li>
  
</ul>
---
Do we have a winner...?

<p class="fragment">Stop! We've forgotten about videos.</p>
---
H.264-Video in image elements

```html
<img src="images/explosion/explosion-h264.mp4">
```

<video src="images/explosion/explosion-h264.mp4" data-autoplay loop muted class="comic-border"></video>
---
<ul>
  <li>✅ 24 bit of colors supported!</li>
  <li>❌ No transparency supported (only in [WebM](https://developers.google.com/web/updates/2013/07/Alpha-transparency-in-Chrome-video?hl=en))</li>
  <li>✅ Small file sizes</li>
  <li>❌ Using video in `<img>` only supported in Safari 💩</li> 
</ul>
---
Last but not least...

<img src="images/AV1_logo.svg" width="1390" height="771" class="fragment">
---
AV1 is the next generation video format

```html
<img src="images/explosion/explosion-av1.mp4">
```

<video src="images/explosion/explosion-av1.mp4" data-autoplay loop muted class="comic-border"></video>
---
<ul>
  <li>✅ Backed by all of the browser vendors</li>
  <li>✅ 40-50% better compression than H.264!</li>
  <li>❌ Supported by Chrome and Firefox, but not yet Safari 💩</li>
  <li>⚠ [There is a polyfill for Safari</a>, though](https://www.singhkays.com/blog/av1-ecosystem-update-july-2019/")</li>
  
</ul>
---
## Animated format size comparison

<canvas data-chart="bar">
<!-- 
{
 "data": {
  "labels": ["Animated GIF","APNG","WebP","MJPEG","H.264","AV1"],
  "datasets": [
   {
    "data": [10105,39459,9387,8920,2562,1278],
    "label": "Filesize in KB","backgroundColor":"rgba(21,174,25,1)"
   }
  ]
 }, 
 "options": { "responsive": "true" }
}
-->
</canvas>
---
## Bringing it all together

```html
<picture>
  <source type="video/av1" 
    src="images/explosion/explosion-av1.mp4">
  <source type="video/mp4" 
    src="images/explosion/explosion-h264.mp4">
  <source type="image/webp" 
    src="images/explosion/explosion.webp">
    <img src="images/explosion/explosion.gif">
</picture>
```
