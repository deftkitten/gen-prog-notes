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
- `margin` - controls the amount of space between an element's border and surrounding elements; if you set an element's margin to a negative value, the element will grow larger.
- `border`

## CSS Selectors

- `.class`
- `#id`
- `*` select all elements
- `element` like p, h2 (select all p's, select all h2's)
