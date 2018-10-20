## Variables

DEFINITION: `--var_name: value`  
ASSIGNMENT: `thing_to_set: var(var_name, fallback);`


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

- `font-size:` 12 px  
- `font-family: FAMILY_NAME, GENERIC_NAME;` so something like 'Helvetica; sans-serif"  
(to import a Google font: '<link href="https://fonts.googleapis.com/css?family=FONT_NAME" rel="stylesheet" type="text/css">')
- `font-weight` (normal, bold, bolder, lighter, [weight value 100-900, 700 is ordinary bold] )
  - inline-equivalent of bold is <strong>text</strong>
- `font-style` (italic (inline equivalent is `<em>`)
- `border-color`, `border-width`, `border-style` (dotted, solid, dotted solid, etc.), `border-radius` (%, px)
- `background-color`
- `padding` - controls the amount of space between the element's content and its border
  - `padding-top`, `padding-right`, `padding-left`, `padding-bottom`
  - `padding: 10px 20px 10px 20px;` (top right bottom left)
- `margin` - controls the amount of space between an element's border and surrounding elements; if you set an element's margin to a negative value, the element will grow larger
  - `margin-top`, `margin-right`, `margin-bottom`, and `margin-left`
  - `margin: 10px 20px 10px 20px;` (top right bottom left)
- `border`
- `text-align` (justify, center, right, left)
- `width` and `height` (relative length units (such as em), absolute length units (such as px), or as a percentage of its containing parent element)
- `text-decoration` underline (inline-equivalent is `<u>`), overline, line-through (inline equivalent is `<s>`)
  - CAN combine these, like `text-decoration: overline red wavy`
- `box-shadow` (applies to `<div>` objects), parameters are `offset-x, offset-y, blur-radius, spread-radius, color`
  - where blur-radius, spread-radius, and color are optional
- `opacity` - 0 (transparent) to 1 (opaque)
- `text-transform`

|Value|Result|
|---|---|
|lowercase|"transform me"|
|uppercase|"TRANSFORM ME"|
|capitalize|"Transform Me"|
|initial|use default value|
|inherit|use text-transform value inherited from parent|
|none|original text|

- `line-height`

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

## Colors

### Hex Color System

__6-DIGITS:__  
#000000 -> each set of two digits represents Red, Green, and Blue. These digits are the brightness of that color.  
EXAMPLES: #FF0000 is 100% red, #00FF00 is 100% green.

__3-DIGITS:__ 
#000 -> only one digit per color, so much fewer options  
EXAMPLES: #F00 is red, #00F is blue

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

SYNTAX: `background: linear-gradient(gradient_direction, color 1, color 2, color 3, ...)`  
EXAMPLE: `background: linear-gradient(90deg, red, yellow, rgb(204, 204, 255));`  
\*Note: MUST use the background property here

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

When elements are positioned to overlap, the element coming later in the HTML markup will, by default, appear on the top of the other elements. However, the `z-index` property can specify the order of how elements are stacked on top of one another
  - must be an integer (i.e. a whole number and not a decimal)
  - higher values for the z-index property of an element move it higher in the stack than those with lower values.
