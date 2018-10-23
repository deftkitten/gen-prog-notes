# HTML Elements

## Main Body

- `<h1>`  heading - should only use one `<h1>` element in a page (for accessibility reasons)
- `<p>`   paragraph
- `<br>`  break line
- `<!--`  comment here    `-->`
- `<head>` this is NOT a header, metadata elements, such as `link`, `meta`, `title`, and `style` typically go inside the head element.
- `<main>` - has an embedded landmark feature that assistive technology can use to quickly navigate to the main content
- `<header>` - used to wrap introductory information or navigation links for its parent tag, and works well around content that's repeated at the top on multiple pages
  - shares the embedded landmark feature you saw with main, allowing assistive technologies to quickly navigate to that content
- `<footer>` - has a built-in landmark feature that allows assistive devices to quickly navigate to it. It's primarily used to contain copyright information or links to related documents that usually sit at the bottom of a page
- `<nav>` - another HTML5 item with the embedded landmark feature for easy screen reader navigation. This tag is meant to wrap around the main navigation links in your page
- `<article>` - a sectioning element, and is used to wrap independent, self-contained content. The tag works well with blog entries, forum posts, or news articles.
- `<section>` - for grouping thematically related content
- `<audio> ` - gives semantic meaning when it wraps sound or audio stream content in your markup
  - Audio content also needs a text alternative to be accessible to people who are deaf or hard of hearing
  - This can be done with nearby text on the page or a link to a transcript
  - the `controls` attribute shows the browser default play, pause, and other controls, and supports keyboard functionality
  - Example: 

    ```
    <audio id="meowClip" controls>
      <source src="audio/meow.mp3" type="audio/mpeg" />
      <source src="audio/meow.ogg" type="audio/ogg" />
    </audio>
    ```
- `<figure>` and `<figcaption>`
  - Example:

```
<figure>
  <img src="roundhouseDestruction.jpeg" alt="Photo of Camper Cat executing a roundhouse kick">
  <br>
  <figcaption>
    Master Camper Cat demonstrates proper form of a roundhouse kick.
  </figcaption>
</figure>
```

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

## Body Elements

| element | purpose | CSS equivalent|
|---|---|---|
|`<strong>`|bold|font-style: bold\
|`<hr>`|separation line|none|
