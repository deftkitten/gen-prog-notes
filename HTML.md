# HTML Elements

## Main Body

- `<h1>`  heading

- `<p>`   paragraph

- `<br>`  break line

- `<!--`  comment here    `-->`

- `<head>` this is NOT a header, metadata elements, such as `link`, `meta`, `title`, and `style` typically go inside the head element.

## Sub-Elements

**image** - `<img src="url" alt="alt text">`

**link to url** - `<a href="url">link title as shown in-line</a>`

**link to internal sections**
```
<a href="#contacts-header">Contacts</a>
...
<h2 id="contacts-header">Contacts</h2>
```

**dead link (to be updated later)** - set `href="#" `

make an image a link: `<a href="#"><img src="url" alt="alt text"></a>`

bulleted ordered list:
```
<ul>
  <li>milk</li>
  <li>cheese</li>
</ul>
```

ordered list:
```
<ol>
  <li>Garfield</li>
  <li>Sylvester</li>
</ol>
```

text field with placeholder: `<input type="text" placeholder="this is placeholder text">`

## Forms

Basic Form:
`<form action="/url-where-you-want-to-submit-form-data"></form>`

Form with radio buttons, checkboxes, required text inputs, and pre-checked items:
```
 <form action="/submit-cat-photo">
   <label><input type="radio" name="indoor-outdoor" checked> Indoor</label>
   <label><input type="radio" name="indoor-outdoor"> Outdoor</label><br>
   <label><input type="checkbox" name="personality" checked> Loving</label>
   <label><input type="checkbox" name="personality"> Lazy</label>
   <label><input type="checkbox" name="personality"> Energetic</label><br>
   <input type="text" placeholder="cat photo URL" required>
   <button type="submit">Submit</button>
 </form>
  ```
  
## Div
  
The div element, also known as a division element, is a general purpose container for other elements.
`<div> ... </div>`

## Basic Page Structure

DOCTYPE tells the browser which version of HTML you're using
```
<!DOCTYPE html>
<html>
  <!-- Your HTML code goes here -->
</html>
```
every HTML document has a `body` element

## ID Attribute
id attributes should be UNIQUE, as they are used by javascript and to select specific elements in CSS
`<h2 id="cat-photo-app">`

class declarations take precedence according to chronological order  
id declarations override class declarations
