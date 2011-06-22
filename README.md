# css-color
css-color is a library for color conversion and manipulation with support for CSS color strings.

```javascript
var color = Color("#77E4FE");

color.red(120).lighten(.5);

console.log(color.hslString());  // "hsl(192, 99%, 110%)"
```	

# Install

#### browser
Download the latest [color.js](http://github.com/harthur/color/downloads). The `Color` object is exported.

#### node
For [node](http://nodejs.org) with [npm](http://npmjs.org):

	npm install color
	
And use with `var Color = require("color")`

# API

## Setters

```javascript
var color = Color("rgb(255, 255, 255)")
```
Pass any valid CSS string into `Color()`, like `"#FFFFFF"`, `"#fff"`, `"white"`, `"hsla(360, 100%, 100%, 0.5)"`

```javascript
var color = Color({r: 255, g: 255, b: 255})
```
You can also pass a hash of color values into `Color()`, keyed on `r` or `red` for example.

```javascript
var color = Color().rgb(255, 255, 255)
```
Load in color values with `rgb()`, `hsl()`, `hsv()`,and `cmyk()`. The arguments can also be an array or hash.

## Getters

```javascript
color.rgb()       // {r: 255, g: 255, b: 255}
```
Get a hash of the rgb values with `rgb()`, similarly for `hsl()`, `hsv()`, and `cmyk()`

```javascript
color.rgbArray()  // [255, 255, 255]
```
Get an array of the values with `rgbArray()`, `hslArray()`, `hsvArray()`, and `cmykArray()`.

```javascript
color.red()       // 255
```
Get the values for individual channels with `alpha`, `red`, `green`, `blue`, `hue`, `saturation` (hsl), `saturationv` (hsv), `lightness`, `cyan`, `magenta`, `yellow`, `black`

```javascript
color.red(100).alpha(0.6)
```
Also set the value of any channel.

## CSS Strings

```javascript
color.hslString()  // "hsl(320, 50%, 100%)"
```

Different CSS String formats for the color are on `hexString`, `rgbString`, `percentString`, `hslString`, and `keyword` (undefined if it's not a keyword color). `"rgba"` and `"hsla"` are used if the current alpha value of the color isn't `1`.

## Manipulation

```javascript
color.greyscale()   // #5CBF54 -> #969696
color.negate()      // rgb(0, 100, 255) -> rgb(255, 155, 0)
color.lighten(0.5)  // hsl(100, 50%, 50%) -> hsl(100, 50%, 75%)
color.darken(0.5)   // hsl(100, 50%, 50%) -> hsl(100, 50%, 25%)

// chaining
color.green(100).greyscale().lighten(0.6)
```

And more to come...