![LineLay](http://i.imgur.com/hs1h6jX.png)
LineLay is a CSS port of Android's LinearLayout, a layout system that works very well when you need to save space to fit content in small screens.
It's not a grid system but have many similarities. It's main advantage is the vertical abilities: you can do everything you do horizontally.

## Orientation
You are able to control your rows the same way you control your columns, make use of it using nested elements with different orientations.

### .horiz
Elements inside it will be organized horizontally, like columns.

### .verti
Elements inside it will be organized vertically, like rows.

## Sizing
You can define fixed or dynamic sizes.

### .weight-{number}
Controls the weight of the element compared to it's siblings. Siblings with same weight will occupy the remaining space of it's parent equaly, a weight-2 will occupy twice the space of a weight-1.

### .w-{number}
The element will have a fixed width, w-25 will have width: 25px everytime, this doesn't count on weight sum, so elements that use weight will have to use other space.

### .h-{number}
The element will have a fixed height, h-25 will have height: 25px everytime, this doesn't count on weight sum, so elements that use weight will have to use other space.

### .w-wrap
The element will use as many space it needs.

### .h-wrap
The element will use as many space it needs.

### .w-window
The element will have the browser window's width.

### .h-window
The element will have the browser window's height.

### .w-full
width: 100%, usually this is not necessary, but in specific cases will be useful (with .truncate maybe).

### .h-full
height: 100%, usually this is not necessary, but in specific cases will be useful.

### .max-w-{number}
Defines the max width.

### .max-h-{number}
Defines the max height.

## Margin
Margin's can take too much space sometimes, so we define it with fixed values. Weight sum will not count it, like any other fixed value.

### .m-{number}
Defines the margin of all sides.

### .mx-{number}
Defines the left and right margin.

### .my-{number}
Defines the top and bottom margin.

### .mt-{number}
Defines the top margin.

### .mr-{number}
Defines the right margin.

### .mb-{number}
Defines the bottom margin.

### .ml-{number}
Defines the left margin.

### .gutter-{number}
Defines margins between all children elements.

## Padding
Just like margin, padding is defined with fixed values.

### .p-{number}
Defines the padding of all sides.

### .px-{number}
Defines the left and right padding.

### .py-{number}
Defines the top and bottom padding.

### .pt-{number}
Defines the top padding.

### .pr-{number}
Defines the right padding.

### .pb-{number}
Defines the bottom padding.

### .pl-{number}
Defines the left padding.

## Self Alignment
You can define alignment of the element compared with it's parent.

### .self-top
Aligns the element to the top of the parent. To be used only inside a `.horiz`.

### .self-left
Aligns the element to the left of the parent. To be used only inside a `.verti`.

### .self-bottom
Aligns the element to the bottom of the parent. To be used only inside a `.horiz`.

### .self-right
Aligns the element to the right of the parent. To be used only inside a `.verti`.

### .self-center
Aligns the element to the center of the parent. Can be used inside `.horiz` or `.verti`.

### .self-baseline
Aligns the element to the baseline of the parent. To be used only inside a `.horiz`.

### .self-start
Aligns the element at the start of the parent. If the parent is `.horiz`, then `.self-start` will align it to the top, if the parent is `.verti`, to the left.

### .self-end
Aligns the element at the end of the parent. If the parent is `.horiz`, then `.self-end` will align it to the top, if the parent is `.verti`, to the top.

## Items Alignment
You can align all items inside the element at once.

### .items-center
Aligns the children elements to the center of this element, horizontally and vertically. To be used with `.horiz` or `.verti`.

### .items-center-top
Aligns the children elements to the center-top of this element. To be used with `.horiz` or `.verti`.

### .items-center-bottom
Aligns the children elements to the center-bottom of this element. To be used with `.horiz` or `.verti`.

### .items-left-center
Aligns the children elements to the left-center of this element. To be used with `.horiz` or `.verti`.

### .items-left-top
Aligns the children elements to the left-top of this element. To be used with `.horiz` or `.verti`.

### .items-left-bottom
Aligns the children elements to the left-bottom of this element. To be used with `.horiz` or `.verti`.

### .items-right-center
Aligns the children elements to the right-center of this element. To be used with `.horiz` or `.verti`.

### .items-right-top
Aligns the children elements to the right-top of this element. To be used with `.horiz` or `.verti`.

### .items-right-center
Aligns the children elements to the right-center of this element. To be used with `.horiz` or `.verti`.

## Text Utils
Some useful classes to deal with text.

### .text-center
Aligns the text inside the element. Avoid using this to center other kind of elements.

### .truncate
Truncate the text putting "..." in the end if the text is too big for it's container. Maybe you will need to put it inside the container and use `.w-full`.

### .line-h-{number}
Defines the line height, usefull to center text vertically. Avoid using this to center other kind of elements.

## Scroll
Try to use a scrollable div inside your page instead of letting the whole page scrollable, you will have more control over what is fixed and what is scrollable.

### .scroll
Allow scroll in all directions.

### .x-scroll
Allow vertical scroll.

### .y-scroll
Allow horizontal scroll.

## Above the surface
You can easily create floating elements above the others with 3 classes.

### .absolute
The element is positioned relative to its first positioned (not static) ancestor element.

### .fixed
The element is positioned relative to the browser window.

### .relative
The child element is positioned relative to its normal position, so `left: 20px` adds 20 pixels to the element's LEFT position.

### Positioning those elements

##### .top-{number}
##### .right-{number}
##### .bottom-{number}
##### .left-{number}

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

### .desktop
Show this element only on desktop devices.

### .desktop-tablet
Show this element only on desktop or tablet devices.

### .mobile
Show this element only on mobile devices.

### .mobile-tablet
Show this element only on mobile or tablet devices.

### .des-{class}
Modify any class described here with `.des-` to make it work only on desktop devices.

### .tab-{class}
Modify any class described here with `.tab-` to make it work only on tablet devices.

### .mob-{class}
Modify any class described here with `.mob-` to make it work only on mobile devices.