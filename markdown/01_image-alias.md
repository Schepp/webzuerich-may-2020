<h1 class="boom">1.</h1>
---
<pre><code class="liveCoding xml" data-livecoding-id="markup-alias" contenteditable>&lt;img src="images/batman-white.jpg"&gt;</code></pre>

<div id="markup-alias" style="max-width: 75%; padding: 10px; background: #fff; border: 1px solid #000"></div>
---
## &lt;image&gt;

> The HTML &lt;image&gt; element is an obsolete remnant of an ancient version of HTML lost in the mists of time.<br>   
Browsers will attempt to map this to &lt;img&gt;.<br>  
However, that doesn't mean this is a good idea to use. It's not.

[MDN: &lt;image&gt;: The obsolete Image element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/image) 
---
## What is it good for?
---
## Format switching back in the days...

<pre><code class="xml">&lt;svg width="450" height="600"&gt;
 &lt;image xlink:href="images/captain-marvel-illustration.svg"
        
        src="images/captain-marvel-illustration.png"
        
        width="450"
        height="600"&gt;
&lt;/svg&gt;</code></pre>
---
## Nowadays: Useless!

(unless you wanna bypass HTML filters)
