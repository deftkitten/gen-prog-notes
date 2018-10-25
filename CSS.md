# Basic CSS

## Variables

DEFINITION: `--var_name: value`  
ASSIGNMENT: `thing_to_set: var(var_name, fallback);`

## Pseudo-Elements

`::before` and `::after` - used to add something before or after a selected element

## Classes  
reusable styles that can be added to HTML elements.

DEFINITION:
```
.myClass {
    color: blue;
  }
```

ASSIGNMENT: `<h2 class="blue-text">CatPhotoApp</h2>`

\*Note: can apply multiple classes to one element

## CSS Properties

FONT
- `font-size:` 12 px  
- `font-family: FAMILY_NAME, GENERIC_NAME;` so something like 'Helvetica; sans-serif"  
(to import a Google font: '<link href="https://fonts.googleapis.com/css?family=FONT_NAME" rel="stylesheet" type="text/css">')
- `font-weight` (normal, bold, bolder, lighter, [weight value 100-900, 700 is ordinary bold] )
  - inline-equivalent of bold is <strong>text</strong>
- `font-style` (italic (inline equivalent is `<em>`)
- `text-align` (justify, center, right, left)
- `text-decoration` underline (inline-equivalent is `<u>`), overline, line-through (inline equivalent is `<s>`)
  - CAN combine these, like `text-decoration: overline red wavy`
- `text-transform`

BORDER, MARGIN, & PADDING
- `border-color`, `border-width`, `border-style` (dotted, solid, dotted solid, etc.), `border-radius` (%, px)
- `padding` - controls the amount of space between the element's content and its border
  - `padding-top`, `padding-right`, `padding-left`, `padding-bottom`
  - `padding: 10px 20px 10px 20px;` (top right bottom left)
- `margin` - controls the amount of space between an element's border and surrounding elements; if you set an element's margin to a negative value, the element will grow larger
  - `margin-top`, `margin-right`, `margin-bottom`, and `margin-left`
  - `margin: 10px 20px 10px 20px;` (top right bottom left)
- `border`

CONTAINER
- `background-color`
- `width` and `height` (relative length units (such as em), absolute length units (such as px), or as a percentage of its containing parent element)
- `box-shadow` (applies to `<div>` objects), parameters are `offset-x, offset-y, blur-radius, spread-radius, color`
  - where blur-radius, spread-radius, and color are optional
- `opacity` - 0 (transparent) to 1 (opaque)
- `transform-text` : table below 

|Value|Result|
|---|---|
|lowercase|"transform me"|
|uppercase|"TRANSFORM ME"|
|capitalize|"Transform Me"|
|initial|use default value|
|inherit|use text-transform value inherited from parent|
|none|original text|

- `line-height`
- `transform: [operation as follows:]`
  - `scale( [scale_factor] )` - handy for `:hover:` conditions bc it makes the hovered item bigger, smaller, etc.
  - `skewX( [skew factor in degrees] )` - must be in degrees
  - `skewY( [skew factor in degrees] )`

## CSS Selectors

- `.class`
- `#id`
- `*` select all elements
- the elements themselves like `p`, `h2` (selects all p's, selects all h2's)
- attribute - this selector matches and styles elements with a specific attribute value
  ```
  [type='radio'] {
    margin: 20px 0px 20px 0px;
  }
  ```
- `:root` - acts as a container for your entire HTML document, in the same way that an html element is a container for the body element.  
  - By creating your variables in :root, they will be available throughout the whole web page.
- pseudo-class - keyword that can be added to selectors, in order to select a specific state of the element.
  - for example, the styling of an anchor tag can be changed for its hover state using the :hover pseudo-class selector  
  ```
  a:hover {
  color: red;
  }
  ```

## Units

**Absolute** units (like px and inches) are approximated lengths given a screen's resolution
**Relative** units (em based on the size of the font)

Order of CSS style precedence:
1. `!important`
2. in-line style
3. id declaration
4. class declaration

## Pattern Backgrounds

SYNTAX: `background: url( [url] );`  
EXAMPLE: `background: url(https://i.imgur.com/MJAkxbh.png);`  

## Colors

### Hex Color System  

6-DIGITS: #000000 -> each set of two digits represents Red, Green, and Blue. These digits are the brightness of that color.  
EXAMPLE: `#FF0000` is 100% red, `#00FF00` is 100% green.

3-DIGITS: #000 -> only one digit per color, so much fewer options  
EXAMPLE: `#F00` is red, `#00F` is blue

### RGB functions

**Regular**  
SYNTAX: `rgb( [amt red] , [amt green] , [amt blue] )`  
EXAMPLE: `rcb(244, 14, 0)`

**With Defined Opacity**  
SYNTAX: `rbga( [amt red] , [amt green] , [amt blue] , [amt opacity])`  
EXAMPLE: `rgba(15, 23, 250, 40%)`

### HSL function

SYNTAX: `hsl( [hue], [saturation], [lightness] )`
  - **hue** is the color itself, ranging from 0-360 in degrees on the color wheel
  - **saturation** - amount of gray
  - **lightness** - amount of white or black - ranging from 0% (black) to 100% (white), where 50% is the normal color  

EXAMPLES:
    
|Color	|HSL|
|---|---|
|red	|`hsl(0, 100%, 50%)`|
|yellow	|`hsl(60, 100%, 50%)`|
|green	|`hsl(120, 100%, 50%)`|
|cyan	|`hsl(180, 100%, 50%)`|
|blue	|`hsl(240, 100%, 50%)`|
|magenta	|`hsl(300, 100%, 50%)`|

### Gradients

**Regular Gradient**  
SYNTAX: `background: linear-gradient(gradient_direction, color 1, color 2, color 3, ...)`  
EXAMPLE: `background: linear-gradient(90deg, red, yellow, rgb(204, 204, 255));`  
\*Note: MUST use the background property here

**Repeating Gradient**  
SYNTAX: `background: repeating-linear-gradient(grad_direction, color stop_location, color stop_location, ...)`  
EXAMPLE: `background: repeating-linear-gradient(90deg, yellow 0px, blue 40px, green 40px, red 80px);` 

## Positioning

CSS treats each HTML element as its own box, which is usually referred to as the **CSS Box Model**
- Block-level items automatically start on a new line (think headings, paragraphs, and divs)
- inline items sit within surrounding content (like images or spans)
- this default layout of elements in this way is called the **normal flow** of a document, but CSS offers the position property to override it.

ASSIGMENTS:
- `relative` - allows you to specify how CSS should move it relative to its current position in the normal flow of the page
  - set properites like `bottom`, `top`, `left`, `right`
  - changing an element's position to relative does not remove it from the normal flow - other elements around it still behave as if that item __were in its default position__.
- `absolute` - locks the element in place relative to its parent container
  - unlike the relative position, this removes the element from the normal flow of the document, so surrounding items __ignore it__.
  - can also apply offsets to this
- `fixed` - a type of absolute positioning that locks an element relative to the browser window. Similar to absolute positioning, it's used with the CSS offset properties and also removes the element from the normal flow of the document. Other items no longer "realize" where it is positioned, which may require some layout adjustments elsewhere.
- `float` - this is NOT set with `position`, specified like `float: left`
  - removed from the normal flow of a document and pushed to either the left or right of their containing parent element
  - commonly used with the width property to specify how much horizontal space the floated element requires.
- center a block element horizontally. One way to do this is to set its `margin` to a value of `auto`.
  - this method works for images, too -> images are inline elements by default, but can be changed to block elements when you set the `display` property to `block`.
  
## Overlapping Elements

The element coming later in the HTML markup will, by default, appear on the top of the other elements. 

However, the `z-index` property can specify the order of how elements are stacked on top of one another
  - must be an integer (i.e. a whole number and not a decimal)
  - higher values for the z-index = higher in stack

## Animation

The animation properties control how the animation should behave and the @keyframes rule controls what happens during that animation. There are eight animation properties in total:
- animation-name
- animation-duration  

**@keyframes** specifies exactly what happens within the animation over the duration, defines specific "frames" during the animation, with percentages ranging from 0% to 100%

EXAMPLE:  
```
#anim { 
  animation-name: colorful;
  animation-duration: 3s;
}
@keyframes colorful {
  0% {
    background-color: blue;
  }
  100% {
    background-color: yellow;
  }
}
```

\*Note: `#anim` is simply an id reference

### Fill Mode of an Animation  

`animation-fill-mode: forwards` sets the final style of the element to the final stage of the animation (rather than reverting to first state)

### Creating Movement  

When `position` is defined, such as `fixed` or `relative`, the CSS offset properties `right`, `left`, `top`, and `bottom` can be used in animation rules to create movement.

```
@keyframes rainbow {
  0% {
    background-color: blue;
    top: 0px;
  }
  50% {
    background-color: green;
    top: 50px;
  }
  100% {
    background-color: yellow;
    top: 0px;
  }
}
```  

### Animation Properties  

- `animation-iteration-count` - set to `infinite` if want perpetual animation
- `animation-timing-function` - controls how quickly an animated element changes over the duration of the animation
  - `ease` - which starts slow, speeds up in the middle, and then slows down again in the end
  - `ease-out` - which is quick in the beginning then slows down
  - `ease-in` - which is slow in the beginning, then speeds up at the end
  - `linear` - which applies a constant animation speed throughout.
- **Bezier Curve** - The shape of the curve represents how the animation plays out. The curve lives on a 1 by 1 coordinate system. The X-axis of this coordinate system is the duration of the animation (think of it as a time scale), and the Y-axis is the change in the animation.
  - set `animation-timing-function` to `cubic-bezier( pt1_x, pt1_y, pt2_x, pt2_y)`
  - `cubic-bezier( .25, .25, .75, .75)` is linear  
  
  
# Applied Accessibility

## Make Elements Only Visible to a Screen Reader by Using Custom CSS

This happens when information is in a visual format (like a chart), but screen reader users need an alternative presentation (like a table) to access the data. So you essentially hide the table from view.

EXAMPLE:
```
.sr-only {
  position: absolute;
  left: -10000px;
  width: 1px;
  height: 1px;
  top: auto;
  overflow: hidden;
}
```

\*Note: the following do NOT do the same thing: `display: none` or `visibility: hidden` hides content for everyone, including screen reader users

## Improve Readability with High Contrast Text  

- Web Content Accessibility Guidelines (WCAG) recommend at least a 4.5 to 1 contrast ratio for normal text. 1:1 is the same color, 21:1 is the extreme (white on black)  

- Be careful when choosing text color, close colors can be thought of as neighbors on the color wheel, and those combinations should be avoided when conveying important information.

# Responsive Web Design Principles

## Using `media` query

- Media Queries change the presentation of content based on different viewport sizes. The viewport is a user's visible area of a web page, and is different depending on the device used to access the site.  
- Media Queries consist of a media type, and if that media type matches the type of device the document is displayed on, the styles are applied. 

GENERAL USE: `@media (max-width: 100px) { /* CSS Rules */ }` or `@media (min-height: 350px) { /* CSS Rules */ }`
EXAMPLE: 
```
@media (max-height: 800px) {
    p {
      font-size: 10px;
    }
  }
```

## Make an Image Responsive  

```
img {
  max-width: 100%;
  display: block;
  height: auto;
}
```

- `max-width` property of 100% scales the image to fit the width of its container - image won't stretch wider than its original width
- `block` changes the image from inline element (its default) to a block element on its own line
- `auto` maintains original aspect ratio

## Use a Retina Image for Higher Resolution Displays

simplest way to make your images appear "retina" (and optimize them for retina displays) is to define their width and height values as only half of what the original file is.  

## Make Typography Responsive  

Instead of using em or px to size text, you can use **viewport units** for responsive typography. **Viewport units** are relative to the viewport dimensions (width or height) of a device, and percentages are relative to the size of the parent container element. The four viewort units are:
- `vw: 10vw` would be 10% of the viewport's width
- `vh: 3vh` would be 3% of the viewport's height
- `vmin: 70vmin` would be 70% of the viewport's smaller dimension (height vs. width)
- `vmax: 100vmax` would be 100% of the viewport's bigger dimension (height vs. width)

# CSS Flexbox  

## Basis  

Placing the CSS property `display: flex`; on an element allows you to use other flex properties to build a responsive page.

## Adjust Flex Containers (NOT applied to specific items)

### Using `flex-direction`

`display: flex` turns elements into a flex container -> possible to align any children of that element into rows or columns  
- Creating a row will align the children horizontally, and creating a column will align the children vertically.
- options for `flow-direction`:
  - `row` (this is DEFAULT)
  - `column`
  - `row-reverse`
  - `column-reverse`  
  
### Align Elements Along Main Axis Using `justify-content`  

**main axis:** the direction the flex items are arranged
-> set `justify-content` to:
- `center` - aligns all the flex items to the center inside the flex container
- `flex-start` - aligns items to the start of the flex container
- `flex-end` - aligns items to the end of the flex container
- `space-between` - aligns items to the center of the main axis, with extra space placed between the items. The first and last items are pushed to the very edge of the flex container
- `space-around` - similar to space-between but the first and last items are not locked to the edges of the container, the space is distributed around all the items

### Align Elements Along Cross Axis Using `align-items`  

This is the analogue of `justify-content`, but for the **cross axis** (axis perpendicular to main axis)  
CSS offers the `align-items` property to align flex items along the cross axis
- For row, it tells CSS how to push the items in the entire row up or down within the container
- for column, how to push all the items left or right within the container

Options for `align-items` are:
- `flex-start` - aligns items to the start of the flex container (for rows -> top of container; columns -> left of container)
- `flex-end` - aligns items to the end of the flex container. (rows -> bottom of container; columns -> right of container)
- `center` - align items to the center
- `stretch` - stretch the items to fill the flex container
- `baseline` - align items to their baselines. (**Baseline** is a text concept, think of it as the line that the letters sit on)

### Wrap a Row or Column Using `flex-wrap`

CSS flexbox has a feature to split a flex item into multiple rows (or columns). By default, a flex container will fit all flex items together. For example, a row will all be on one line.  

Extra items move into a new row or column. The break point of where the wrapping happens depends on the size of the items and the size of the container.

-> set `flex-wrap` to:
- `nowrap` - this is the default setting, and does not wrap items
- `wrap` - wraps items from left-to-right if they are in a row, or top-to-bottom if they are in a column
- `wrap-reverse` - wraps items from bottom-to-top if they are in a row, or right-to-left if they are in a column

## Affect Individual Flex Items (NOT applied to container)

### Control Size of Items When Container Shrinks: `flex-shrink`  

Items shrink when width of parent container is smaller than combined widths of all flex items within it

-> Operates like a ratio: the higher the number, the more it will shrink compared to the other items in the container
- For example, if one item has a `flex-shrink = 1` and other has `flex-shrink = 3`, the one with the value of 3 will shrink three times as much as the other  

### Control Size of Items When Container Expands: `flex-grow`  

opposite of `flex-shrink`

### Set Initial Size of Item: `flex-basis`

Specifies initial size of item before CSS makes adjustments (with `flex-shrink` or `flex-grow`)

-> Takes usual units (px, em, %, etc.), and `auto` which sizes items based on content (if no content, will not appear)

### Set Grow, Shrink, and Basis with One Line  

DEFINITION: `flex: [flex-grow val] [flex-shrink val] [flex-basis val];`  
EXAMPLE: `flex: 1 0 10px;` will set the item to `flex-grow: 1`;, `flex-shrink: 0`;, and `flex-basis: 10px;`  
DEFAULT: `flex: 0 1 auto;`  

### Rearrange Items: `order`  

By default, items will appear in the same order they come in the source HTML. The property takes numbers as values, and negative numbers can be used.

### Adjust Each Item Individually: `align-self`  

Allows you to adjust each item's alignment individually, instead of setting them all at once  

-> accepts the same values as `align-items` and will override any value set by the `align-items` property

\*Note: `float`, `clear`, and `vertical-align` do not work on flex items.

# CSS Grid  


## Affect Grid Container  

DEFINITION: `display: grid` -> apply to container  
SET COLUMNS: with `grid-template-columns`  
```
.container {
  display: grid;
  grid-template-columns: 50px 50px;
}
```  
SET ROWS: with `grid-template-rows`  

- can use absolute (px) and relative units (em, etc.), and:
  - `fr` - sets the column or row to a fraction of the available space
  - `auto` - sets the column or row to the width or height of its content automatically
  - `%` - adjusts the column or row to the percent width of its container  
  
EXAMPLE: `grid-template-columns: auto 50px 10% 2fr 1fr;`

Insert Gaps (optional): `grid-column-gap` and `grid-row-gap`
- `grid-gap: [row_gap_val] [col_gap_val]` combines these two into one definition -> single value sets both

## Affect Individual Grid Elements  

The hypothetical horizontal and vertical lines that create the grid are referred to as lines.  

Control the amount of columns an item will consume -> set `grid-column: [start_line] / [end_line];`  
  EXAMPLE: `grid-column: 1 / 3;`  
  
Control the amount of rows an item will consume -> set `grid-row: [start_line] / [end_line];`
  EXAMPLE: `grid-row: 1 / 3;`

### Justify Content Within Cells  

**Horizontally** 
-> set `justify-self` to:
- `stretch` - DEFAULT - content fills the whole width of the cell   
- `start` - aligns the content at the left of the cell
- `center` - aligns the content in the center of the cell
- `end` - aligns the content at the right of the cell

**Vertically** 
-> set `align-self` (same options as `justify-self`)

### Divide the Grid Into Custom Areas  

group cells of your grid together into areas using `grid-template-areas` on the container  
EXAMPLE:  
```
grid-template-areas:
  "header header header"
  "advert content content"
  "footer footer footer";
```  
- use a period (.) to designate an empty cell in the grid  

### Assign Items to Custom Areas

You can place an item in your custom area by referencing the name you gave it:
```
.item1 { grid-area: header; }
```  

### Assign Items to Non-Defined Areas  

Create an area on the fly for an item to be placed like this: `item1 { grid-area: [horizontal_start_line] / [vertical_start_line] / [horizontal_end_line] / [vertical_end_line]; }`  

EXAMPLE:
```
item1 { grid-area: 1/1/2/4; }
```  

### Use `repeat` Function to Quickly Define Many Columns / Rows  

`grid-template-rows: repeat( [num_rows] , [row_width] );`
EXAMPLE:  
```
grid-template-rows: repeat(100, 50px);
```  

Repeat _multiple_ values with the `repeat` function, and insert the function amongst other values when defining a grid structure  
`grid-template-columns: repeat(2, 1fr 50px) 20px;` is same as `grid-template-columns: 1fr 50px 1fr 50px 20px;`


### Limit Item Size Using `minmax`  

use `minmax` in conjunction with `grid-template-columns` & `grid-template-rows` to limit the size of items when the grid container changes size  
-> specify the acceptable size range for your item: `minmax( [min_size], [max_size] )`  

EXAMPLE:
`grid-template-columns: 100px minmax(50px, 200px);`  
In the code above, grid-template-columns is set to create two columns; the first is 100px wide, and the second has the minimum width of 50px and the maximum width of 200px.  

### Using `auto-fill` with `repeat` Function  

This allows you to automatically insert as many rows or columns of your desired size as possible depending on the size of the container  
USAGE: `grid-template-columns: repeat(auto-fill, 3px)` (will create as many 3px columns will fit)  

You can also create flexible layouts when combining auto-fill with minmax: `repeat(auto-fill, minmax(60px, 1fr));`  

### `auto-fit` vs `auto-fill`  

When the container's size exceeds the size of all the items combined, `auto-fill` keeps inserting empty rows or columns and pushes your items to the side, while `auto-fit` collapses those empty rows or columns and stretches your items to fit the size of the container  

\*Note: If your container can't fit all your items on one row, it will move them down to a new one.
