if you wanted all `h2` elements to be red, you would add a style rule that looks like this:

```
<style>
  h2 {color: red;}
</style>
```

## Variables

DEFINITION: `--var_name: value`  
TO ASSIGN: `...: var(var_name, fallback);


## Classes  
reusable styles that can be added to HTML elements.

defined like:
```
.blue-text {
    color: blue;
  }
```

then applied like:
`<h2 class="blue-text">CatPhotoApp</h2>`

can apply multiple classes to one element

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
- the element itself like `p`, `h2` (select all p's, select all h2's)
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


order of CSS style precedence:
- `!importatnt`
- in-line style
- id declaration
- class declaration

# Colors

## Hex Color System

__6-DIGITS__: #000000 -> each set of two digits represents Red, Green, and Blue. These digits are the brightness of that color.  
SO #FF0000 is 100% red. #00FF00 is 100% green.

__3-DIGITS__: #F00 is red, #00F is blue (much fewer options)

## RGB functions

- rgb( [amt red] , [amt green] , [amt blue] )
- rbga( [amt red] , [amt green] , [amt blue] , [amt opacity])


