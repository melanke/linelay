![LineLay](http://i.imgur.com/VddYz5e.png)


LineLay is a CSS port of Android's LinearLayout, a layout system that works very well when you need to save space to fit content in small screens. It's main advantage is the vertical abilities: you can do everything you do horizontally.

# Installation

### Npm
```
npm install --save linelay
```

or
### CDN
```
https://cdn.rawgit.com/melanke/linelay/master/linelay.min.css
```
or
### Download
[master.zip](https://github.com/melanke/linelay/archive/master.zip)

# Samples
- **[Complete example with classes on HTML](https://codepen.io/melanke/embed/rwZpPM?height=475&theme-id=dark&default-tab=result&embed-version=2)**
- **[The same example but using @include on Scss](https://codepen.io/melanke/embed/OgrGKO?height=475&theme-id=dark&default-tab=result&embed-version=2)**
- **[Golden Ratio!](https://codepen.io/melanke/embed/YQgKRx?theme-id=dark&default-tab=result,html&embed-version=2)**
- **[Browse our codepen collection](https://codepen.io/collection/DyVKbb) or click on the images in samples below.**

# Using with Sass
- If you import `linelay.scss` you will have only the variables, extensions and mixins.
- If you import `defaultBuild.scss` you will have the classes too. (**RECOMENDED**)
- If you want to customize the sizes you can import `builder.scss` and call `build` include, check `defaultBuild.scss` code as an example

# Docs
- [Orientation](#orientation)
- [Sizing](#sizing)
- [Margin](#margin)
- [Padding](#padding)
- [Self Alignment](#self-alignment)
- [Items Alignment](#items-alignment)
- [Text Utils](#text-utils)
- [Font Utils](#font-utils)
- [Scroll](#scroll)
- [Above the surface](#above-the-surface)
- [Sizing](#sizing)
- [Breakpoints](#breakpoints)
- [Force a style](#force-a-style)

## Orientation
You are able to control your rows the same way you control your columns, make use of it using nested elements with different orientations.

### .horiz

Elements inside it will be organized horizontally, like columns.

<sub><sup>With Sass you can use `@include horiz()` or `@include horiz($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/4Ru7keX.png)](https://codepen.io/melanke/embed/ZyVKGg?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .verti
Elements inside it will be organized vertically, like rows.

<sub><sup>With Sass you can use `@include verti()` or `@include verti($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/fGGmihw.png)](https://codepen.io/melanke/embed/WOPbqJ?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .nowrap
The `.horiz` has `flex-wrap: wrap` by default, it means it will break the line when needed. You can disable this behaviour with `.nowrap`

<sub><sup>With Sass you can use `@include nowrap()` or `@include nowrap($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/B3v51zl.png)](https://codepen.io/melanke/embed/xPPxRM?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

## Sizing
You can define fixed or dynamic sizes.

### .weight-{number}
Controls the weight of the element compared to it's siblings. Siblings with same weight will occupy the remaining space of it's parent equaly, a weight-2 will occupy twice the space of a weight-1.

<sub><sup>With Sass you can use `@include weight($number)` or `@include weight($number, $mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/QXQ2fN6.png)](https://codepen.io/melanke/embed/GEzJKE?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .w-{number}
The element will have a fixed width, w-25 will have width: 25px everytime, this doesn't count on weight sum, so elements that use weight will have to use other space.

<sub><sup>With Sass you can use `width: {number}px`, `@include w($number)` or `@include w($number, $mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/4njGGz8.png)](https://codepen.io/melanke/embed/pwGJEY?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .h-{number}
The element will have a fixed height, h-25 will have height: 25px everytime, this doesn't count on weight sum, so elements that use weight will have to use other space.

<sub><sup>With Sass you can use `height: {number}px`, `@include h($number)` or `@include h($number, $mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/qhL0tzH.png)](https://codepen.io/melanke/embed/BZMNQx?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .w-auto
The element will use as many space it needs.

<sub><sup>With Sass you can use `@include w-auto()` or `@include w-auto($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/GszepGe.png)](https://codepen.io/melanke/embed/bRzdgj?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .h-auto
The element will use as many space it needs.

<sub><sup>With Sass you can use `@include h-auto()` or `@include h-auto($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/m59BrIp.png)](https://codepen.io/melanke/embed/xrMGLO?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .w-window
The element will have the browser window's width. You can also use `.min-w-window`.

<sub><sup>With Sass you can use `width: 100vw`, `@include w-window()` or `@include w-window($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/hRIyUMp.png)](https://codepen.io/melanke/embed/KqJpXY?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .h-window
The element will have the browser window's height. You can also use `.min-h-window`.

<sub><sup>With Sass you can use `height: 100vh`, `@include h-window()` or `@include h-window($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/SzMuKur.png)](https://codepen.io/melanke/embed/RgvXBW?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .w-full
**width: 100%**, usually this is not necessary, but in specific cases will be useful (with .truncate maybe).

<sub><sup>With Sass you can use `width: 100%`, `@include w-full()` or `@include w-full($mediaquery)`<sup><sub>

### .h-full
**height: 100%**, usually this is not necessary, but in specific cases will be useful.

<sub><sup>With Sass you can use `height: 100%`, `@include h-full()` or `@include h-full($mediaquery)`<sup><sub>

### .max-w-{number}
Defines the max width.

<sub><sup>With Sass you can use `max-width: {number}px`, `@include max-w($number)` or `@include max-w($number, $mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/kCNCrgx.png)](https://codepen.io/melanke/embed/JJxgaq?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .max-h-{number}
Defines the max height.

<sub><sup>With Sass you can use `max-height: {number}px`, `@include max-h($number)` or `@include max-h($number, $mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/IjeT9kP.png)](https://codepen.io/melanke/embed/XgOvyy?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .min-w-{number}
Defines the min width. You can also use `.min-w-window`.

<sub><sup>With Sass you can use `min-width: {number}px`, `@include min-w($number)` or `@include min-w($number, $mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/DBCxBIA.png)](https://codepen.io/melanke/embed/bYYeLR?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .min-h-{number}
Defines the min height. You can also use `.min-h-window`.

<sub><sup>With Sass you can use `min-height: {number}px`, `@include min-h($number)` or `@include min-h($number, $mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/ESrhFtP.png)](https://codepen.io/melanke/embed/MOOeVB?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

## Margin
Margin's can take too much space sometimes, so we define it with fixed values. Weight sum will not count it, like any other fixed value.

[![Imgur](http://i.imgur.com/LaCu6eJ.png)](https://codepen.io/melanke/embed/OgdKdp?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .m-{number}
Defines the margin of all sides.

<sub><sup>With Sass you can use `margin: {number}px`, `@include m($number)` or `@include m($number, $mediaquery)`<sup><sub>

### .mx-{number}
Defines the left and right margin.

<sub><sup>With Sass you can use `@include mx($number)` or `@include mx($number, $mediaquery)`<sup><sub>

### .my-{number}
Defines the top and bottom margin.

<sub><sup>With Sass you can use `@include my($number)` or `@include my($number, $mediaquery)`<sup><sub>

### .mt-{number}
Defines the top margin.

<sub><sup>With Sass you can use `margin-top: {number}px`, `@include mt($number)` or `@include mt($number, $mediaquery)`<sup><sub>

### .mr-{number}
Defines the right margin.

<sub><sup>With Sass you can use `margin-right: {number}px`, `@include mr($number)` or `@include mr($number, $mediaquery)`<sup><sub>

### .mb-{number}
Defines the bottom margin.

<sub><sup>With Sass you can use `margin-bottom: {number}px`, `@include mb($number)` or `@include mb($number, $mediaquery)`<sup><sub>

### .ml-{number}
Defines the left margin.

<sub><sup>With Sass you can use `margin-left: {number}px`, `@include ml($number)` or `@include ml($number, $mediaquery)`<sup><sub>

### .gutter-{number}
Defines margins between all children elements. Consider using `.items-mb-{number}` to help when the line breaks.

<sub><sup>With Sass you can use `@include x-gutter($number)`, `@include y-gutter($number)`, `@include x-gutter($number, $mediaquery)` or `@include y-gutter($number, $mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/qqHWGet.png)](https://codepen.io/melanke/embed/weOwvr?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

## Padding
Just like margin, padding is defined with fixed values.

[![Imgur](http://i.imgur.com/perjrT0.png)](https://codepen.io/melanke/embed/bRZbNY?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .p-{number}
Defines the padding of all sides.

<sub><sup>With Sass you can use `padding: {number}px`, `@include p($number)` or `@include p($number, $mediaquery)`<sup><sub>

### .px-{number}
Defines the left and right padding.

<sub><sup>With Sass you can use `@include px($number)` or `@include p($number, $mediaquery)`<sup><sub>

### .py-{number}
Defines the top and bottom padding.

<sub><sup>With Sass you can use `@include py()` or `@include py($number, $mediaquery)`<sup><sub>

### .pt-{number}
Defines the top padding.

<sub><sup>With Sass you can use `padding-top: {number}px`, `@include pt($number)` or `@include pt($number, $mediaquery)`<sup><sub>

### .pr-{number}
Defines the right padding.

<sub><sup>With Sass you can use `padding-right: {number}px`, `@include pr($number)` or `@include pr($number, $mediaquery)`<sup><sub>

### .pb-{number}
Defines the bottom padding.

<sub><sup>With Sass you can use `padding-bottom: {number}px`, `@include pb($number)` or `@include pb($number, $mediaquery)`<sup><sub>

### .pl-{number}
Defines the left padding.

<sub><sup>With Sass you can use `padding-left: {number}px`, `@include pl($number)` or `@include pl($number, $mediaquery)`<sup><sub>

## Self Alignment
You can define alignment of the element compared with it's parent.

[![Imgur](http://i.imgur.com/0Oyz5Mf.png)](https://codepen.io/melanke/embed/PjLYWJ?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .self-top
Aligns the element to the top of the parent. To be used only inside a `.horiz`.

<sub><sup>With Sass you can use `@include self-start()` or `@include self-start($mediaquery)`<sup><sub>

### .self-left
Aligns the element to the left of the parent. To be used only inside a `.verti`.

<sub><sup>With Sass you can use `@include self-start()` or `@include self-start($mediaquery)`<sup><sub>

### .self-bottom
Aligns the element to the bottom of the parent. To be used only inside a `.horiz`.

<sub><sup>With Sass you can use `@include self-end()` or `@include self-end($mediaquery)`<sup><sub>

### .self-right
Aligns the element to the right of the parent. To be used only inside a `.verti`.

<sub><sup>With Sass you can use `@include self-end()` or `@include self-end($mediaquery)`<sup><sub>

### .self-center
Aligns the element to the center of the parent. Can be used inside `.horiz` or `.verti`.

<sub><sup>With Sass you can use `@include self-center()` or `@include self-center($mediaquery)`<sup><sub>

### .self-baseline
Aligns the element to the baseline of the parent. To be used only inside a `.horiz`.

<sub><sup>With Sass you can use `@include self-baseline()` or `@include self-baseline($mediaquery)`<sup><sub>

### .self-start
Aligns the element at the start of the parent. If the parent is `.horiz`, then `.self-start` will align it to the top, if the parent is `.verti`, to the left.

<sub><sup>With Sass you can use `@include self-start()` or `@include self-start($mediaquery)`<sup><sub>

### .self-end
Aligns the element at the end of the parent. If the parent is `.horiz`, then `.self-end` will align it to the top, if the parent is `.verti`, to the top.

<sub><sup>With Sass you can use `@include self-end()` or `@include self-end($mediaquery)`<sup><sub>

## Items Alignment
You can align all items inside the element at once.

### .items-center
Aligns the children elements to the center of this element, horizontally and vertically. To be used with `.horiz` or `.verti`.

<sub><sup>With Sass you can use `@include items-center()` or `@include items-center($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/PndsWMb.png)](https://codepen.io/melanke/embed/rwRqXa?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .items-center-top
Aligns the children elements to the center-top of this element. To be used with `.horiz` or `.verti`.

<sub><sup>With Sass you can use `@include items-center-start()` or `@include items-center-start($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/DnXCbBX.png)](https://codepen.io/melanke/embed/yXwRmd?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .items-center-bottom
Aligns the children elements to the center-bottom of this element. To be used with `.horiz` or `.verti`.

<sub><sup>With Sass you can use `@include items-center-end()` or `@include items-center-end($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/r3h3lYK.png)](https://codepen.io/melanke/embed/awMQoN?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .items-left-center
Aligns the children elements to the left-center of this element. To be used with `.horiz` or `.verti`.

<sub><sup>With Sass you can use `@include items-start-center()` or `@include items-start-center($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/1RmBl1c.png)](https://codepen.io/melanke/embed/VWRVZW?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .items-left-top
Aligns the children elements to the left-top of this element. To be used with `.horiz` or `.verti`.

<sub><sup>With Sass you can use `@include items-start()` or `@include items-start($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/Pv5vLG6.png)](https://codepen.io/melanke/embed/NgJEKE?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .items-left-bottom
Aligns the children elements to the left-bottom of this element. To be used with `.horiz` or `.verti`.

<sub><sup>With Sass you can use `@include items-start-end()` or `@include items-start-end($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/clPP69n.png)](https://codepen.io/melanke/embed/yXwQBd?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .items-right-center
Aligns the children elements to the right-center of this element. To be used with `.horiz` or `.verti`.

<sub><sup>With Sass you can use `@include items-end-center()` or `@include items-end-center($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/udOA9Ta.png)](https://codepen.io/melanke/embed/gREQOe?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .items-right-top
Aligns the children elements to the right-top of this element. To be used with `.horiz` or `.verti`.

<sub><sup>With Sass you can use `@include items-end-start()` or `@include items-end-start($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/Sg99lGw.png)](https://codepen.io/melanke/embed/awMQzZ?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .items-right-center
Aligns the children elements to the right-center of this element. To be used with `.horiz` or `.verti`.

<sub><sup>With Sass you can use `@include items-end-center()` or `@include items-end-center($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/ExKiz3Y.png)](https://codepen.io/melanke/embed/GEewgx?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .items-space-around
Arrange elements with equal space around them. To be used with `.horiz` or `.verti`.

<sub><sup>With Sass you can use `@include items-space-around()` or `@include items-space-around($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/G7efVYp.png)](https://codepen.io/melanke/embed/wPPzwp?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .items-space-between
Arrange elements with equal space between them. To be used with `.horiz` or `.verti`.

<sub><sup>With Sass you can use `@include items-space-between()` or `@include items-space-between($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/3mqnD6A.png)](https://codepen.io/melanke/embed/vWWXEg?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .items-mb-{number}
Adds a bottom margin to all children elements, useful when you are usign `horiz` and `gutter`, so when the children wraps to a second line they get a margin between them.

<sub><sup>With Sass you can use `@include items-mb($number)` or `@include items-mb($number, $mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/MudwGC8.png)](https://codepen.io/melanke/embed/REdLaN?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

## Text Utils
Some useful classes to deal with text.

### .text-center
Aligns the text to the center inside the element. Avoid using this to center other kind of elements.

<sub><sup>With Sass you can use `text-align: center`, `@include text-center()` or `@include text-center($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/lOlj4cb.png)](https://codepen.io/melanke/embed/yXwQym?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .text-left
Aligns the text to the left inside the element.

<sub><sup>With Sass you can use `text-align: left`, `@include text-left()` or `@include text-left($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/vclsHiR.png)](https://codepen.io/melanke/embed/rYYMVg?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .text-right
Aligns the text to the right inside the element.

<sub><sup>With Sass you can use `text-align: right`, `@include text-right()` or `@include text-right($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/bPajyJF.png)](https://codepen.io/melanke/embed/NwwRGM?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .text-justify
Aligns the text justifying inside the element.

<sub><sup>With Sass you can use `text-align: justify`, `@include text-justify()` or `@include text-justify($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/mRuQO2L.png)](https://codepen.io/melanke/embed/JOORGY?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .truncate
Truncate the text putting "..." in the end if the text is too big for it's container. Maybe you will need to put it inside the container and use `.w-full`.

<sub><sup>With Sass you can use `@include truncate()` or `@include truncate($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/4CwZwR3.png)](https://codepen.io/melanke/embed/OgqaVw?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .line-h-{number}
Defines the line height, usefull to center text vertically. Avoid using this to center other kind of elements.

<sub><sup>With Sass you can use `line-height: {number}px`, `@include line-h($number)` or `@include line-h($number, $mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/btHE9B2.png)](https://codepen.io/melanke/embed/bRZQVQ?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

## Font Utils
Useful classes to control the fonts

### .f-bold and .f-normal
Use `.f-bold` to make the text bold or `.f-normal` to make it normal.

[![Imgur](http://i.imgur.com/ooWleBH.png)](https://codepen.io/melanke/embed/KbEXeR?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .ff-primary and .ff-secondary
You can use this classes to quickly swap between fonts, but to make it work properly you will need to define the font-face in your CSS.

<sub><sup>With Sass you can use `@include ff($fontname)` or `@include ff($fontname, $mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/VhOEe0Q.png)](https://codepen.io/melanke/embed/MZxEzP?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .fs-{number} and it's alias
Changes the font-size using a number or a name

<sub><sup>With Sass you can use `@include fs($number)` or `@include fs($number, $mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/qKRDDCi.png)](https://codepen.io/melanke/embed/NeJwqz?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

## Scroll
Try to use a scrollable div inside your page instead of letting the whole page scrollable, you will have more control over what is fixed and what is scrollable.

### .scroll
Allow scroll in all directions.

<sub><sup>With Sass you can use `overflow: scroll`, `@include scroll()` or `@include scroll($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/iAGQCSS.png)](https://codepen.io/melanke/embed/jwJorz?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .x-scroll
Allow vertical scroll.

<sub><sup>With Sass you can use `@include x-scroll()` or `@include x-scroll($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/e141oH7.png)](https://codepen.io/melanke/embed/jwJowK?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

### .y-scroll
Allow horizontal scroll.

<sub><sup>With Sass you can use `@include y-scroll()` or `@include y-scroll($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/LIP8tvd.png)](https://codepen.io/melanke/embed/NgJVay?theme-id=dark&default-tab=result,html&embed-version=2)
<br/>Click to explore

## Above the surface
You can easily create floating elements above the others with 3 classes.

### .absolute
The element is positioned relative to its first positioned (not static) ancestor element. It's recommended to be placed as the last element on Html.

<sub><sup>With Sass you can use `position: absolute`, `@include absolute()` or `@include absolute($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/7yln4LA.png)](https://codepen.io/melanke/embed/qjwBZR?theme-id=dark&default-tab=result,html&embed-version=2)

### .fixed
The element is positioned relative to the browser window.

<sub><sup>With Sass you can use `position: fixed`, `@include fixed()` or `@include fixed($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/Bg1nlC6.png)](https://codepen.io/melanke/embed/MoRrOo?theme-id=dark&default-tab=result,html&embed-version=2)

### .relative
The child element is positioned relative to its normal position, so `left: 20px` adds 20 pixels to the element's LEFT position.

<sub><sup>With Sass you can use `@include relative()` or `@include relative($mediaquery)`<sup><sub>

[![Imgur](http://i.imgur.com/lnWWIfP.png)](https://codepen.io/melanke/embed/KqYZZa?theme-id=dark&default-tab=result,html&embed-version=2)

### Positioning those elements

[![Imgur](http://i.imgur.com/zrP3IRE.png)](https://codepen.io/melanke/embed/mwgpXZ?theme-id=dark&default-tab=result,html&embed-version=2)

##### .top-{number}

<sub><sup>With Sass you can use `top: {number}px`, `@include top($number)` or `@include top($number, $mediaquery)`<sup><sub>

##### .right-{number}

<sub><sup>With Sass you can use `right: {number}px`, `@include right($number)` or `@include right($number, $mediaquery)`<sup><sub>

##### .bottom-{number}

<sub><sup>With Sass you can use `bottom: {number}px`, `@include bottom($number)` or `@include bottom($number, $mediaquery)`<sup><sub>

##### .left-{number}

<sub><sup>With Sass you can use `left: {number}px`, `@include left($number)` or `@include left($number, $mediaquery)`<sup><sub>

##### .z-{number} or it's alias

Changes the Z order, overlapping elements with a larger z-index cover those with a smaller one.

`.z-0`; 
`.z-auto`; 
`.z-1` or `.z-pop`; 
`.z-2` or `.z-header`; 
`.z-3` or `.z-scrim`; 
`.z-4` or `.z-modal`; 
`.z-5` or `.z-alert`; 
`.z-6` or `.z-high`; 
`.z-7` or `.z-higher`; 
`.z-99999` or `.z-highest`; 
`.z-low` (-1); 
`.z-lower` (-2); 
`.z-lowest` (-99999)

## Breakpoints
Breakpoints are useful when you want to change the layout depending on user's device. 

<table>
	<tr>
	    <th>Desktop</th>
	    <th>Tablet</th>
	    <th>Mobile</th>
	</tr>
	<tr>
	    <td>window width greater than 768px</td>
	    <td>window width between 544px and 768px</td>
	    <td>window width less than 544px</td>
	</tr>
</table>

[![Imgur](http://i.imgur.com/DqlpXxN.png)](https://codepen.io/melanke/embed/ZJzjaR?theme-id=dark&default-tab=result,html&embed-version=2)

### .desktop
Show this element only on desktop devices.

<sub><sup>With Sass you can use `@extend %desktop`<sup><sub>

### .tablet
Show this element only on tablet devices.

<sub><sup>With Sass you can use `@extend %tablet`<sup><sub>

### .mobile
Show this element only on mobile devices.

<sub><sup>With Sass you can use `@extend %mobile`<sup><sub>

### .desktop-tablet
Show this element only on desktop or tablet devices.

<sub><sup>With Sass you can use `@extend %desktop-tablet`<sup><sub>

### .mobile-tablet
Show this element only on mobile or tablet devices.

<sub><sup>With Sass you can use `@extend %mobile-tablet`<sup><sub>

### .des-{class}
Modify any class described here with `.des-` to make it work only on desktop devices.

<sub><sup>With Sass you can pass `$only-desktop` in the last argument of the mixin<sup><sub>

### .tab-{class}
Modify any class described here with `.tab-` to make it work only on tablet devices.

<sub><sup>With Sass you can pass `$only-tablet` in the last argument of the mixin<sup><sub>

### .mob-{class}
Modify any class described here with `.mob-` to make it work only on mobile devices.

<sub><sup>With Sass you can pass `$only-mobile` in the last argument of the mixin<sup><sub>

## Force a style
Modify any class described here with `.force-` to add an `!important` and have a CSS rule priority
