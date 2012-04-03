<h1>Adaptable</h1>
<p>Creating a responsive photo gallery is tough. You need to calculate again and again and again. You're a web designer/developer and (face it) math is not your specialty. This Sass mixin allows you to add a simple bit of code in your stylesheet to dynamically calculate widths and margins for your photos.</p>

<h2>Demo</h2>
<p>Because every thing needs to be demonstrated. <a href="http://www.reusserdesign.com/blog/demo/adaptable/index.html" target="_blank">View the demo</a></p>

<h2>Browser Support</h2>
<p>Adaptable relies heavily on CSS selectors. You will need selectivizr.js to run this under Internet Explorer 7-8.</p>
<ul>
	<li>Internet Explorer 9+</li>
	<li>Internet Explorer 7-8 (with selectivizr.js)</li>
	<li>Firefox 3.6+</li>
	<li>Chrome 9+</li>
	<li>Safari 4+</li>
</ul>

<h2>How To Use</h2>
<p>In your HTML, create a gallery using an unordered list. For example:</p>
<pre>
	&lt;!-- jQuery + Selectivizr adds support for nth-child in IE browsers 7-8 -->
	&lt;script src="http://ajax.googleapis.com/ajax/libs/jquery/1.7.1/jquery.min.js"></script>
	&lt;script src="scripts/selectivizr.js"></script>
	&lt;!-- end selectivizr.js -->
	
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

<p>In your scss or sass document, add the grid mixin:</p>
<pre>
	@mixin grid($items) {
		list-style: none;
		margin: 0;
		overflow: hidden;
		padding: 0;
		li {
			float: left;
			&:nth-child(1n) {
				margin: 5% 0 0 0;
			}
			@if $items > 1 {
				&:nth-child(1n) {
					margin: (5% / ($items - 1)) (5% / ($items - 1)) 0 0;
				}
				width: (95% / $items);
				*width: (94% / $items);
			}
			&:nth-child(#{$items}n) {
				margin-right: 0;
			}
			&:nth-child(-n+#{$items}) {
				margin-top: 0;
			}
			img, a {
				float: left;
			}
			a {
				text-align: center;
				width: 100%;
			}
		}
	}
</pre>

<p>Next, apply the mixin to your containing unordered list and specify how many images should be in each row. For example:</p>
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

<h3>1.0.1 - April 2, 2012</h3>
<ul>
	<li>Fixed a numerous amount of browser issues</li>
	<li>Enhanced documentation</li>
	<li>Added selectivizr.js to support earlier versions of IE</li>
</ul>

<h3>1.0 - March 29, 2012</h3>
<ul>
	<li>Initial release. Hooray!</li>
</ul>