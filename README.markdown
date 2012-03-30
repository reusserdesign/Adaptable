<h1>Adaptable</h1>
<p>Creating a responsive photo gallery is tough. You need to calculate again and again and again. You're a web designer/developer and (face it) math is not your specialty. This Sass mixin allows you to add a simple bit of code in your stylesheet to dynamically calculate widths and margins for your photos.</p>

<h2>Demo</h2>
</p>Because every thing needs to be demonstrated. <a href="http://www.reusserdesign.com/blog/demo/adaptable/index.html">View the demo</a></p>

<h2>How To Use</h2>
<p>In your HTML, create a gallery using an unordered list. For example:</p>
<pre>
	&lt;ul>
		&lt;li>&lt;a href="#">&lt;img src="images/beaker.png" />&lt;/a>&lt;/li>
		&lt;li>&lt;a href="#">&lt;img src="images/beaker.png" />&lt;/a>&lt;/li>
		&lt;li>&lt;a href="#">&lt;img src="images/beaker.png" />&lt;/a>&lt;/li>
		&lt;li>&lt;a href="#">&lt;img src="images/beaker.png" />&lt;/a>&lt;/li>
		&lt;li>&lt;a href="#">&lt;img src="images/beaker.png" />&lt;/a>&lt;/li>
		&lt;li>&lt;a href="#">&lt;img src="images/beaker.png" />&lt;/a>&lt;/li>
		&lt;li>&lt;a href="#">&lt;img src="images/beaker.png" />&lt;/a>&lt;/li>
		&lt;li>&lt;a href="#">&lt;img src="images/beaker.png" />&lt;/a>&lt;/li>
		&lt;li>&lt;a href="#">&lt;img src="images/beaker.png" />&lt;/a>&lt;/li>
		&lt;li>&lt;a href="#">&lt;img src="images/beaker.png" />&lt;/a>&lt;/li>
	&lt;/ul>
</pre>

<p>In your scss or sass document, add the grid mixin and specify how many images should be in each row. For example:</p>
<pre>
	ul {
		@include grid(4);
	}
</pre>

<p>Done.</p>

<p>When you are in a media query, you can now readjust your gallery to include fewer or more images. For example:</p>
<pre>
	@media (max-width: 768px) {
		ul {
			@include grid(3);
		}
	}
</pre>

<h2>Latest Changes</h2>

<h3>1.0 - March 29, 2012</h3>
<ul>
	<li>Initial release. Hooray!</li>
</ul>