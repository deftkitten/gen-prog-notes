if you wanted all `h2` elements to be red, you would add a style rule that looks like this:

```
<style>
  h2 {color: red;}
</style>
```

**Classes** are reusable styles that can be added to HTML elements.

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
- `width`
- `border-color`, `border-width`, `border-style` (dotted, solid, dotted solid, etc.), `border-radius` (%, px)
- `background-color`
- `padding` - controls the amount of space between the element's content and its border
  - `padding-top`, `padding-right`, `padding-left`, `padding-bottom`
  - `padding: 10px 20px 10px 20px;` (top right bottom left)
- `margin` - controls the amount of space between an element's border and surrounding elements; if you set an element's margin to a negative value, the element will grow larger
  - `margin-top`, `margin-right`, `margin-bottom`, and `margin-left`
  - `margin: 10px 20px 10px 20px;` (top right bottom left)
- `border`

## CSS Selectors

- `.class`
- `#id`
- `*` select all elements
- `element` like p, h2 (select all p's, select all h2's)
- attribute selectors - this selector matches and styles elements with a specific attribute value
```
[type='radio'] {
  margin: 20px 0px 20px 0px;
}
```

## Units

**Absolute** units (like px and inches) are approximated lengths given a screen's resolution
**Relative** units (em based on the size of the font)
