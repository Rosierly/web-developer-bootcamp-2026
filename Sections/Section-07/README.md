# Section 07 - The World of CSS Selectors

## Notes

### Element Selector
###### Selects elements by their tag name.
```css
button {
    font-size: 30px;
}
```
---

### Selector List
###### Combines multiple selectors using a comma.
```css
h1, h2 {
    color: magenta;
}
```
---

### Universal Selector
###### Selects all elements in the document. Generally avoid using it unnecessarily.
```css
* {
    color: pink;
}
```
---

### ID Selector
###### Selects an element by its unique `id`. An `id` should be used only once per page, for one unique element.
```html
<button id="signup">Sign Up</button>
```
```css
#signup {
    background-color: #1d3557;
    color: #f1faee;
}
```
---

### Class Selector
###### Selects elements by their `class`. A class can be used on multiple elements.
```html
<span class="tag">New</span>
<span class="tag">Featured</span>
<a class="tag" href="/products">Sale</a>
```
```css
.tag {
    color: background-color: #e63946;
    color: #f1faee;
    font-size: 16px;
}
```
---

### Descendent Selector
###### Selects elements nested inside another element using a space between the selectors.
```html
<section>
    <span>
        <a href="#">Learn More</a>
    </span>
</section>
```
```css
/* Selects all <a> elements inside <section>, regardless of how deeply they are nested. */
section a { color: #457b9d; }

/* We could also be more specific */
section span a {
    color: #457b9d;
}
```
---

### Adjacent Selector
###### Selects an element that is immediately preceded by another element at the same level, using `+`.
```html
<form>
    <input type="text" placeholder="Enter your name">
    <button>Submit</button>
</form>
```
```css
/* Selects <button> elements that come right after an <input> */
input + button {
    background-color: pink;
}
```
---

### Direct Descendent Selector
###### Selects elements that are direct children of another element using `>`.
```html
<footer>
    <a href="#">Privacy Policy</a>
</footer>
```
```css
footer > a {
    color: #a8dadc;
}
```
---

### Attribute Selector
###### Selects elements based on the presence or value of an HTML attribute.
```html
<input type="password">
<input type="text">

<section class="post">
    <h2>My Post</h2>
</section>
```
```css
input[type="password"] {
    color: greenyellow;
}

/* Selects <section> elements with class="post" */
section[class="post"] {
    background-color: purple;
}

/* Instead, we could do this to select the class but only on <section> elements, not all elements with the "post" class */
section.post {
    background-color: purple;
}
```
---

### Pseudo Classes
###### A keyword added to a selector that specifies a special state or condition of the selected element(s).
- `:active` - Selects an element while it is being activated.
- `:checked` - Selects a checked checkbox or radio button.
- `:first` - Selects the first matching element.
- `:first-child` - Selects an element that is the first child of its parent.
- `:hover` - Selects an element while the mouse is over it.
- `:not()` - Selects elements that do not match the given selector.
- `:nth-child()` - Selects elements based on their position among their siblings.
- `:nth-of-type()` - Selects elements based on their position among siblings of the same type.
```css
.post button:hover {
    background-color: #e63946;
    color: #1d3557;
}

.post button:active {
    background-color: #02c39a;
}

/* Remove the default underline */
a {
    text-decoration: none;
}

/* Add color and underline when hovered */
a:hover {
    color: orange;
    text-decoration: underline;
}

/* Selects every even .post to create an alternating, table-like effect */
.post:nth-of-type(2n) {
    background-color: #dfe8dc;
}
```
---

### Pseudo Elements
###### A keyword added to a selector that lets you style a specific part of a selected element(s) or insert content before or after it.
- `::after` - Inserts content after an element's content.
- `::before` - Inserts content before an element's content.
- `::first-letter` - Selects the first letter of an element.
- `::first-line` - Selects the first line of an element.
- `::selection` - Styles the portion of an element selected by the user.
```css
h2::first-letter {
    font-size: 50px;
}

h2::before { 
    content: "→ "; 
}

p::selection {
    background-color: #fcbf49;
}
```
---
### Summary: CSS Selectors
| Selector             | What It Selects                                      | Example                  |
| -------------------- | ---------------------------------------------------- | ------------------------ |
| **Element**          | Elements by tag name                                 | `button`                 |
| **Selector List**    | Multiple selectors                                   | `h1, h2`                 |
| **Universal**        | All elements                                         | `*`                      |
| **ID**               | An element by its unique `id`                        | `#signup`                |
| **Class**            | Elements by their `class`                            | `.tag`                   |
| **Descendant**       | Elements nested inside another element               | `section a`              |
| **Adjacent Sibling** | An element immediately after another element         | `input + button`         |
| **Direct Child**     | Elements that are direct children of another element | `footer > a`             |
| **Attribute**        | Elements based on an attribute                       | `input[type="password"]` |
| **Pseudo-Class**     | Elements in a specific state or condition            | `a:hover`                |
| **Pseudo-Element**   | A specific part of an element                        | `h2::first-letter`       |
---


### The CSS Cascade
###### The order in which CSS rules are declared and linked can affect which styles are applied. When two rules have the same specificity, the rule that comes later in the CSS wins.
```css
h1 {
    color: red;
}

h1 {
    color: purple;
}
/* purple wins because it comes later */
```
**Note**:
The same principle applies when using multiple CSS files. If two rules have the same specificity, the rule from the stylesheet that is loaded later wins.

---

### CSS Specificity
###### Specificity determines which CSS rule the browser applies when multiple rules target the same element. The more specific selector wins.

#### General Specificity Hierarchy
- ID > Class, Attribute & Pseudo-Class > Element & Pseudo-Element
```css
.post button:hover {
    background-color: #e63946;
    color: #f1faee;
}

button:hover {
    background-color: olive;
    font-size: 10px;
}
/* .post button:hover is more specific, so its background-color will be applied */
```
---

### Inline Styles
###### Inline styles are CSS styles applied directly to an HTML element using the `style` attribute. They have higher specificity than ID selectors.
```html
<button id="signup" style="color:blue">Sign up</button>
<!-- The inline style wins over a regular rule in an external stylesheet -->
```
---

### Important Rule
###### `!important` gives a declaration higher priority in the cascade. It can override regular declarations regardless of specificity. It should be used sparingly.
```html
<button id="signup">Sign Up</button>
```
```css
#signup {
    background-color: blue;
}

button {
    background-color: firebrick !important;
}
/* Here, #signup is more specific than button, but the !important declaration wins. */
```
---

### Summary: CSS Cascade & Specificity Priority
|    Priority | CSS Rule                | Example                                                                                                                                                                  |
| ----------: | ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1 — Highest | `!important`            | `button { color: red !important; }`                                                                                                                                      |
|           2 | Inline styles           | `<button style="color: red">`                                                                                                                                            |
|           3 | **Specificity**         | **ID** > **Class, Attribute & Pseudo-Class** > **Element & Pseudo-Element**<br>`#signup { color: red; }`<br>`.button`, `[type="text"]`, `:hover`<br>`button`, `::before` |
|  4 — Lowest | Position / Source Order | When rules have equal priority and specificity, the rule that comes later wins.                                                                                          |
---

### CSS Inheritance
###### Some CSS properties are inherited from a parent element by its children. If a child doesn't have its own value, it can inherit the value from its parent.
```css
body {
    color: orange;
}
```
**Note**: Not all CSS properties are inherited. For example, border is not inherited by default.

---

### TIP: Chrome Dev Tools & CSS
You can use Chrome DevTools to see which CSS rules are applied. Overridden rules are shown with a strikethrough. You can also test different styles, but changes are not saved.

---

## References
- *[Coolors Color Palette Website](https://coolors.co/palettes/trending)*
- *[Specificity Calculator Tool](https://specificity.keegan.st/)*
