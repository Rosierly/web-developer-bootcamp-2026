# Section 03 - HTML: The Essentials

## Notes

### HTML (**H**yper**T**ext **M**arkup **L**anguage)

###### HTML is a markup language used to structure and organize content in a document.It uses elements and tags to define the structure and meaning of content.
---

### HTML Elements
###### To write HTML, we pick from a set of standard Elements that all browsers recognize.
#### Common Elements include:
- `<p>` element - represents a paragraph of text
- `<h1>` element - represents the main header of a page
- `<img>` element - embeds an image
- `<form>` element - represents a form
---

### HTML Tags
###### We create elements by writing tags. Most (but not all) elements consists of an opening and closing tag.
```html
<p>I am a paragraph</p>
```
---

### Paragraph Elements
###### The HTML `<p>` element represents a paragraph of text and groups related text together.
```html
<p>The <b>chicken</b> (Gallus gallus domesticus) is the domesticated form of the red junglefowl (Gallus gallus), originally native to Southeast Asia.</p>
<!-- <b> element makes the text bold -->

<p>
It was first domesticated around 8,000 years ago and is one of the most common and widespread domesticated animals in the world. Chickens are primarily kept for their meat and eggs, though they are also kept as pets.
</p>
```
---

### HTML Headings
###### The HTML `<h1>`-`<h6>` elements represent six levels of section headings. `<h1>` is the highest section level and `<h6>`is the lowest.
```html
<!-- Use only one <h1> per page, it should be the main heading of the page. -->
<h1>Chicken</h1>
    <h2>Terminology</h2>
    <h2>General biology and habitat</h2>
        <h3>Behavior</h3>
            <h4>Social behaviour</h4>
            <h4>Broodiness</h4>
```
---

### HTML Boilerplate (HTML Skeleton)
###### HTML documents follow a standard basic structure, often called an HTML skeleton.
```html
<!DOCTYPE html>  <!-- the version of HTML the code was written in, declares that the document uses HTML5 -->
<html lang="en">  <!-- root element of the document (the attribute lang stands for language) -->

    <head> <!-- contains machine-readable information about the document -->
        <meta charset="UTF-8"> <!-- meta tag for the character set encoding of the webpage -->
        <title>Chicken - Coltipedia</title>
    </head>

    <body> <!-- all the content of an HTML document goes inside the body element -->
        <h1>Chicken</h1>
    </body>
    
</html>
```
- **Shortcut for Boilerplate in VS Code**:  
Type `!` and hit `Enter` on the first selection
---

### HTML Lists
###### HTML lists are used to group related items together. They can be unordered or ordered.

- #### Unordered List
    ###### The HTML `<ul>` element represents an unordered list of items, typically rendered as a bulleted list.
    ```html
    <h2>Breeds</h2>
    <ul>
        <li>Silkie</li>  <!-- this is a list item -->
        <li>Polish</li>
        <li>Easter Egger</li> 
        <li>Rhode Island Red</li> 
    </ul>
    ```
    ```html
    <!-- Nested Unordered List -->
    <ul>
        <li>Bantam
            <ul>
                <li>Silkie</li>  
                <li>Polish</li>
            </ul>
        </li>

        <li>Standard
            <ul>
                <li>Easter Egger</li> 
                <li>Rhode Island Red</li> 
            </ul>
        </li>
    </ul>
    ```

- #### Ordered List
    ###### The HTML `<ol>` element represents an ordered list of items, typically rendered as a numbered list.
    ```html
    <h2>Steps</h2>
    <ol>
        <li>Open the browser</li>
        <li>Open Developer Tools</li>
        <li>Inspect the page</li>
    </ol>
    ```
---

### HTML Anchor Tags
###### The HTML `<a>` element with its `href` attribute, creates a hyperlink to web pages, files, email addresses, location in the same page, or anything else a URL can adress.
```html
<!-- Link to a website -->
<a href="https://www.google.com/">I am a link to Google.</a>

<!-- Link to another document in the same folder -->
<a href="about.html">About Page</a>

<!-- Link inside a paragraph, <a> is an inline element.-->
<p>The <b>chicken</b> (Gallus gallus domesticus) is the domesticated form of the <a href="https://en.wikipedia.org/wiki/Red_junglefowl">red junglefowl</a> (Gallus gallus), originally native to Southeast Asia.</p>
```
**Note:** `href` stands for Hypertext Reference.

---

### HTML Images
###### The HTML `<img>` element embeds an image into the document. It is a void element and does not require a closing tag.
```html
<img src="stevie_chicks.jpg" alt="My pet chicken, Stevie Chicks">

<!-- We can change the width using an attribute, but this is generally bad practice. -->
<img src="stevie_chicks.jpg" width="200">
<!-- Better practice: use inline CSS to change the width. -->
<img src="stevie_chicks.jpg" style="width: 200px;">
```
**Note:** The `alt` attribute holds a text description of the image, which isn't mandatory but is incredibly useful for accessibility - screen readers read this description out to their users so they know what the image means.

---

### Comments
###### HTML comments are notes in the code that are not displayed in the browser.
```html
<!-- This is an HTML comment -->
```
**Shortcut:**
- `Command + /` on Mac
- `Ctrl + /` on Windows
---

### VS Code Formatting On Save - Auto-format
###### Automatically formats and indents our HTML so it looks clean and consistent.

1. Launch the Command Palette and search for **Format Document**:
   - `Ctrl + Shift + P` on Windows
   - `Command + Shift + P` on Mac

2. Or use the **shortcut**:
   - `Shift + Option + F` on Mac
   - `Shift + Alt + F` on Windows

#### Auto-Format - How to Enable It
- Open **Settings** > search for `format on save` > enable **Editor: Format On Save**
---

### Introduction to Chrome Inspector - Chrome Developer Tools
###### Chrome DevTools allows you to inspect and debug the HTML, CSS, and JavaScript of a webpage.
- Right-click anywhere on the page and select **Inspect**.
- Shortcut: `Ctrl + Shift + I`
- `⋮` > `More tools` > `Developer tools`
---

### Using MDN (Mozilla Developer Network) as a Resource
###### MDN is a developer resource that provides documentation, tutorials, references, and guides for web technologies. It is open source, written for developers, and covers both the basics and advanced topics.
---

### References
- *[MDN Homepage](https://developer.mozilla.org/en-US/)*
- *[MDN HTML Element Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements)*