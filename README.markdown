# Adaptable

Creating a responsive photo gallery is tough. You need to calculate again and again and again. You're a web designer/developer and (face it) math is not your specialty. This Sass mixin allows you to add a simple bit of code in your stylesheet to dynamically calculate widths and margins for your photos.

## How To Use

In your HTML, create a gallery using an unordered list. For example:
	<ul>
		<li><a href="#"><img src="images/beaker.png" /></a></li>
		<li><a href="#"><img src="images/beaker.png" /></a></li>
		<li><a href="#"><img src="images/beaker.png" /></a></li>
		<li><a href="#"><img src="images/beaker.png" /></a></li>
		<li><a href="#"><img src="images/beaker.png" /></a></li>
		<li><a href="#"><img src="images/beaker.png" /></a></li>
		<li><a href="#"><img src="images/beaker.png" /></a></li>
		<li><a href="#"><img src="images/beaker.png" /></a></li>
		<li><a href="#"><img src="images/beaker.png" /></a></li>
		<li><a href="#"><img src="images/beaker.png" /></a></li>
	</ul>

In your scss or sass document, add the grid mixin and specify how many images should be in each row. For example:
	@include grid(4);

Done.

When you are in a media query, you can now readjust your gallery to include fewer or more images. For example:
	@media (max-width: 768px) {
		ul {
			@include grid(3);
		}
	}

## Latest Changes

### 1.0 - March 29, 2012

- Initial release. Hooray!