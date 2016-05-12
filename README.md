# Combatproof Mixins 1.5.1

**Combatproof mixins are a selection of time saving sass mixins and placeholders I use almost everyday since 2014. Some of them come from around the Internet, some of them were coded by myself.**

Some of the descriptions are coming from [http://caniuse.com](Can I Use), some other from [W3Schools](http://www.w3schools.com)

### New in 1.5.2 :
- added `%clearfix` ;
- added `%flex` ;
- added `%inline-block` ;
- added `%stretch` ;
- added `%text-truncate` ;
- removed `@mixin icon` ;
- removed commentary on `@mixin image-2x` ;
- removed commentary on `@mixin opacity` ;
- removed `!global` attributes on `@mixin rbpXX`.

# Documentation

### appearance 

The `appearance` property defines how elements (particularly form controls) appear by default. By setting the value to none the default appearance can be entirely redefined using other CSS properties.

[Compatibility](http://caniuse.com/#feat=css-appearance)

```scss
@mixin appearance($appearance: none){
	-webkit-appearance: $appearance;
	-moz-appearance: $appearance;
	&:-moz-focusring {
		color: transparent;
		text-shadow: 0 0 0 #000;
	}
}
```

### border-radius

Method of making the border corners round. Sets the four corners at the same time. The idea of this mixin is to have a default border radius that you can call anywhere in your CSS for consistency.

[Compatibility](http://caniuse.com/#feat=border-radius)

```scss
@mixin border-radius($radius: 3px){
	border-radius: $radius;
}
```

### border-radiuses

Same as `@mixin border-radius` but you can pass 4 corners in the parameters to have four different corners.

[Compatibility](http://caniuse.com/#feat=border-radius)

```scss
@mixin border-radiuses($radius1: 3px, $radius2: 3px, $radius3: 3px, $radius4: 3px){
	border-radius: $radius1 $radius2 $radius3 $radius4;
}
```

### box-sizing

Method of specifying whether or not an element's borders and padding should be included in size units.

Default value is `border-box`.

[Compatibility](http://caniuse.com/#feat=css3-boxsizing)


```scss
@mixin box-sizing($box-sizing: border-box){
	-webkit-box-sizing: $box-sizing;
	-moz-box-sizing: $box-sizing;
	box-sizing: $box-sizing;
}
```

### clearfix

Clearfix hack to clear floats. Base on a solution by [Thierry Koblentz](http://www.yuiblog.com/blog/2010/09/27/clearfix-reloaded-overflowhidden-demystified/), improved by [Nicolas Gallagher](http://nicolasgallagher.com/micro-clearfix-hack/).

```scss
%clearfix{
	&:before,
	&:after {
		content: " ";
		display: table;
	}
	&:after {
		clear: both;
	}
	* zoom: 1;
}
```

```scss
@mixin clearfix{
	&:before,
	&:after {
		content: " ";
		display: table;
	}
	&:after {
		clear: both;
	}
	* zoom: 1;
}
```

### column-count

Method of flowing information in multiple columns.
The column-count property specifies the number of columns an element should be divided into.

Value is a number, ex `2`.

[Compatibility](http://caniuse.com/#feat=multicolumn)

```scss
@mixin column-count($count){
	-webkit-column-count: $count;
	-moz-column-count: $count;
	column-count: $count;
}
```

### column-gap

The column-gap property specifies the gap between the columns.

Value is a size, ex `40px`.

[Compatibility](http://caniuse.com/#feat=multicolumn)

```scss
@mixin column-gap($gap){
	-webkit-column-gap: $gap;
	-moz-column-gap: $gap;
	column-gap: $gap;
}
```

### column-rule

The column-rule-style property specifies the style of the rule between columns.

Value is a type, ex `solid`.

[Compatibility](http://caniuse.com/#feat=multicolumn)

```scss
@mixin column-rule($rule){
	-webkit-column-rule: $rule;
	-moz-column-rule: $rule;
	column-rule: $rule;
}
```

### flex

Method of positioning elements in horizontal or vertical stacks. This placeholder is used to add prefixes

[Compatibility](http://caniuse.com/#feat=flexbox)

```scss
%flex{
	display: -webkit-flex;
	display: flex;
}
```

```scss
@mixin flex{
	display: -webkit-flex;
	display: flex;
}
```


### flex-flow

The flex-flow property is a shorthand property for the flex-direction and the flex-wrap properties.

Default value is `row wrap`.

[Compatibility](http://caniuse.com/#feat=flexbox)

```scss
@mixin flex-flow($value: row wrap){
	-webkit-flex-flow: $value;
	-moz-flex-flow: $value;
	-ms-flex-flow: $value;
	flex-flow: $value;
}
```

### halo

Halo is a quick way to add a glowing effect. It's a `box-shadow` with white color.

Default value is `0 0 3px white`.

[Compatibility](http://caniuse.com/#feat=css-boxshadow)

```scss
@mixin halo($h-shadow:0, $v-shadow:0, $blur:3px, $color:white){
	-webkit-box-shadow: $h-shadow $v-shadow $blur $color;
	-moz-box-shadow: $h-shadow $v-shadow $blur $color;
	box-shadow: $h-shadow $v-shadow $blur $color;
}
```

### image-2x

Image-retina is use to display retina quality image on background when screen pixel ratio is equal or greater than `1.3`.

Values are `url` (quoted), `width` and `height`.

[Compatibility](http://caniuse.com/#feat=css-media-resolution)

```scss
@mixin image-2x($image, $width, $height) {
	@media (min--moz-device-pixel-ratio: 1.3),
	(-o-min-device-pixel-ratio: 2.6/2),
	(-webkit-min-device-pixel-ratio: 1.3),
	(min-device-pixel-ratio: 1.3),
	(min-resolution: 1.3dppx) {
		/* on retina, use image that's scaled by 2 */
		background-image: url($image);
		background-size: $width $height;
	}
}
```

### inline-block

Provides a cross-browser placeholder to implement `display: inline-block;` (introduced in CSS2 but badly implemented across browsers).

```scss
%inline-block {
	display:inline-block;
	*display:inline;
	zoom:1;
}
```

```scss
@mixin inline-block {
	display:inline-block;
	*display:inline;
	zoom:1;
}
```

### opacity

Provides a CSS fallback for IE when using `opacity`.

```scss
@mixin opacity($opacity) {
	opacity: $opacity;
	$opacity-ie: $opacity * 100;
  filter: alpha(opacity=$opacity-ie);
}
```

### order

Flex property to organize elements orders.

Default value is `1`.

[Compatibility](http://caniuse.com/#feat=flexbox)

```scss
@mixin order($value: 1){
	-webkit-order: $value;
	order: $value;
}
```

### rbpXX

RBP is for Responsive BreakPoints. It defines four breakpoints using media queries, matching with four variables so you can choose your breakpoints easily.

Default value are `$sm: 480px`, `$md: 720px;` `$lg: 960px;` `$xl: 1140px`.

[Compatibility](http://caniuse.com/#feat=css-mediaqueries)

```scss
$sm: 480px;
$md: 720px;
$lg: 960px;
$xl: 1140px;
@mixin rbp($media) {
	@if $media == sm {
		@media screen and (max-width: $sm) { @content; }
	}
	@else if $media == md {
		@media screen and (min-width: $sm+1) { @content; }
	}
	@else if $media == lg {
		@media screen and (min-width: $md+1) { @content; }
	}
	@else if $media == xl {
		@media screen and (min-width: $lg+1) { @content; }
	}
}
```

### rotate

Shortcut for `transform: rotate(Xdeg)`. By [David McFarland](http://codepen.io/sawmac/).

Value is a number ex `45`.

[Compatibility](http://caniuse.com/#feat=transforms2d)

```scss
@mixin rotate ($deg) {
	@include transform(rotate(#{$deg}deg));
}
```

### scale

Shortcut for `transform: scale(X, Y)`. By [David McFarland](http://codepen.io/sawmac/).

Value are numbers, ex `1.2, 1.4`.

[Compatibility](http://caniuse.com/#feat=transforms2d)

```scss
@mixin scale($scalex, $scaley) {
	@include transform(scale($scalex, $scaley));
}

```

### skew

Shortcut for `transform: skew(Xdeg, Ydeg)`. By [David McFarland](http://codepen.io/sawmac/).

Value are number, ex `25, 25`.

[Compatibility](http://caniuse.com/#feat=transforms2d)

```scss
@mixin skew ($x, $y) {
	@include transform(skew(#{$x}deg, #{$y}deg));
}
```

### stretch

Strech is use on a child element having a parent on `position: relative;`. It extends it size to equal the size of the parent. By [David Manson](https://github.com/davidmanson/)

```scss
%stretch{
	position: absolute;
	top: 0;
	right: 0;
	bottom: 0;
	left: 0;
}
```

```scss
@mixin stretch{
	position: absolute;
	top: 0;
	right: 0;
	bottom: 0;
	left: 0;
}
```

### text-truncate

Useful to generate an ellipsis on a text block.

[Compatibility](http://caniuse.com/#feat=text-overflow)

```scss
%text-truncate {
	overflow: hidden;
	text-overflow: ellipsis;
	white-space: nowrap;
}
```

```scss
@mixin text-truncate {
	overflow: hidden;
	text-overflow: ellipsis;
	white-space: nowrap;
}
```

### thumbnail

Generates a thumbnail. You must have the following HTML :
```html
<div class="thumbnail">
	<img src="#" alt="image name">
</div>
```
Then you can use the mixin, specifying width and height of the thumbnail in the parameters. The mixin generate the code so the image takes the size of the thumbnail container.

Values are sizes ex `150px, 150px`.

```scss
@mixin thumbnail($width, $height){
	.thumbnail{
		width: $width;height: $height;
		position: relative;
		img{
			@extend stretch;
			max-width: 100%; max-height: 100%;
			margin: auto;
		}
	}
}
```

### transform

Shortcut for `transform: $value`.

Compatibility depends of the applied [transformation](http://caniuse.com/#search=transform).

```scss
@mixin transform($transforms) {
	-moz-transform: $transforms;
	-o-transform: $transforms;
	-ms-transform: $transforms;
	-webkit-transform: $transforms;
	transform: $transforms;
}
```

### transform-origin

Shortcut for `transform-origin: $value`. Sets a rotated element's base placement.

[Compatibility](http://caniuse.com/#feat=transforms2d)

```scss
@mixin transform-origin ($origin) {
	-moz-transform-origin: $origin;
	-o-transform-origin: $origin;
	-ms-transform-origin: $origin;
	-webkit-transform-origin: $origin;
	transform-origin: $origin;
}

```

### transition

Shortcut for `transition: $value`.

Default values are `all, 0.2s, ease-out`.

[Compatibility](http://caniuse.com/#feat=css-transitions)

```scss
@mixin transition($properties:all, $time:0.2s, $ease:ease-out){
	-webkit-transition: $properties $time $ease;
	-moz-transition: $properties $time $ease;
	-ms-transition: $properties $time $ease;
	-o-transition: $properties $time $ease;
	transition: $properties $time $ease;
}
```

### transitions

Transitions let you pass multiple parameters for multiple transition.

Ex : `@include transitions(color 0.2s ease-out, background-color 0.4s, ease-out)`.

You have to pass the entire transition, there is no default value. It's a shortcut to generate prefixes.

[Compatibility](http://caniuse.com/#feat=css-transitions)

```scss
@mixin transitions($var...){  
	-webkit-transition: $var;
	-moz-transition: $var;
	-ms-transition: $var;
	-o-transition: $var;
	transition: $var;
}
```

### translate

Translate calls the mixin `@mixin transform` to apply a translation. It's a shortcut to add prefixes.

Values are dimensions, ex `100px, 200px`.

[Compatibility](http://caniuse.com/#feat=transforms2d)

```scss
@mixin translate ($x, $y) {
	@include transform(translate($x, $y));
}
```

### user-select

Method of preventing text/element selection using CSS. It's a shortcut to add prefixes.

Default value is `none`.

[Compatibility]()

```scss
@mixin user-select($user-select: none){
	-webkit-user-select: $user-select;
	-moz-user-select: $user-select;
	-ms-user-select: $user-select;
	user-select: $user-select;
}
```

### vertical-align-ghost

This fixes a well-known problem : vertical center an element in a parent with unknown dimensions. It applies **to the parent element**.
I wrote this mixin from Michał Czernow's ghost element method.

Compatibility : IE8+

```scss
@mixin vertical-align-ghost{
	&:before{
		content:'';
		display: inline-block;
		height: 100%;
		vertical-align: middle;
	}
	& > * {display: inline-block;vertical-align: middle;}
}
```

### vertical-align-transform

This is another way to fix the vertical center problem. It applies **to the child element** and it's based this time on translations.

[Compatibility](http://caniuse.com/#feat=transforms2d)

```scss
@mixin vertical-align-transform{
	position: relative;
	left: 50%;
	top: 50%;
	-webkit-transform: translate(-50%,-50%);
	-moz-transform: translate(-50%,-50%);
	-ms-transform: translate(-50%,-50%);
	-o-transform: translate(-50%,-50%);
	transform: translate(-50%,-50%);
}
```



