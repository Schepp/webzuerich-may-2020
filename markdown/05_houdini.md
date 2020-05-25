<h1 class="boom">5.</h1>
---
<pre><code>--custom-property: 1</code></pre>

<p class="fragment">👆 This looks like a number, but really is a dumb string.</p>

<p class="fragment">Therefore, you cannot animate that value.</p>
---
Luckily Houdini brings us the possibility to declare the type of a CSS custom property:

<pre><code>CSS.registerProperty({
  name: '--multiply',
  syntax: '&lt;number&gt;',
  inherits: false,
  initialValue: '0'
});</code></pre>

<p class="fragment">👆 This turns a CSS custom properties from a dumb string into a real number.</p>
---
Now we can animate it.

<pre><code>@keyframes zero-to-one {
  from { 
    --multiply: 0; 
  }
  to   { 
    --multiply: 1;
  }
}</code></pre>
---
And combine it with <code>calc()</code>:

<style>
#css-animated-backgrounds div {
width: 100%;
height: 100%;
}
</style>

<pre><code class="liveCoding css" data-livecoding-id="css-animated-backgrounds" contenteditable>div {
  animation: zero-to-one 1000ms infinite;
  background-image: conic-gradient(
    blue calc(var(--multiply) * 40%), 
    red calc(var(--multiply) * 40%), 
    red calc(var(--multiply) * 70%), 
    yellow calc(var(--multiply) * 70%), 
    yellow calc(var(--multiply) * 90%), 
    transparent calc(var(--multiply) * 90%)
  );
  border-radius: 50%;
  filter: drop-shadow(10px 10px 10px #000);
}</code></pre>

<div id="css-animated-backgrounds" style="position: absolute; top: 0; right: 0; width: 400px; height: 400px;"><div></div></div>
---
Combine it with <code>calc()</code> and <code>-webkit-cross-fade()</code><br>
and you'll have a CSS-only slideshow

<style>
#slideshow div {
  width: 800px; 
  height: 400px;
}
</style>

<pre style="margin-left: 0"><code class="css">@keyframes cross-fade {
  0% { --multiply: 0 }
  50% { --multiply: 1 }
  100% { --multiply: 0 }
}

.slideshow {
  background-image: 
    -webkit-cross-fade(
      url('../images/iron-man.jpg'),
      url('../images/hawkeye.jpg'),
      calc(100% * var(--multiply))
    );
  animation: cross-fade 10000ms infinite;
}</code></pre>

<div id="slideshow" style="position: absolute; right: 0; width: 820px; top: 250px; border: 10px solid #fff; background: #fff; outline: 1px solid #000"><div></div></div>


