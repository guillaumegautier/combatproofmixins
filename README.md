# Combatproof Mixins 1.5

### New in 1.5.1 :
- Added `@mixin border-radiuses` ;
- Removed 3 breakpoints in `@mixin rbpXX` ;
- Removed `@mixin blur` due to poor support ;
- Removed `@mixin border-top-radius` ;
- Removed `@mixin border-right-radius` ;
- Removed `@mixin border-bottom-radius` ;
- Removed `@mixin border-left-radius`.

   **Combatproof mixins are a selection of time savers sass mixins I use almost everyday since 2014. Some of them come from around the Internet, some of them were coded by myself.**

   Most of the descriptions are written by [http://caniuse.com](Can I Use).


# Documentation (in progress)

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

### colum-count

### column-gap

### column-rule

### flex

### flex-flow

### halo

### icon

### image-2x

### inline-block

### opacity

### order

### rbpXX

### rotate

### scale

### skew

### stretch

### text-truncate

### thumbnail

### transform

### transform-origin

### transition

### transitions

### translate

### user-select

### vertical-align-ghost

### vertical-align-transform


