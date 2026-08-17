# Section 04 - HTML: Next Steps & Semantics

## Notes

### Understanding what HTML5 Actually is
###### HTML5 is the fifth major version of HTML, the language used to structure and organize content on web pages.

- #### Living Standard
    The HTML standard is a document that describes how HTML should work.

- #### Role of Browsers
    The standard describes the rules of HTML, but browser actually have to do the work and implement HTML according to these rules.

- #### HTML5
    HTML5 is the latest evolution of the standard that defines HTML. It includes new elements & features for browsers to implement.

---

### Block vs. Inline Elements
###### Inline elements fit in alongside other elements.
###### Block level elements take up the whole "block" of space.
```html
<!-- Inline element: -->
<a href="#">Click me</a>
 
<!-- Block-level element: -->
<p>Hello world</p>
```
**Note:** In Chrome DevTools, inline elements take up only as much space as their content, while block-level elements take up the full line.

---

### `<span>` and `<div>` Elements
###### The HTML Content Division Element `<div>` is a generic block-level container used to group content. It has no effect on the content or layout until styled using CSS.
```html
<div>
  <h2>Chocolate Cake Recipe</h2>
  <p>Mix the flour, sugar, eggs, and milk in a large bowl.</p>
</div>
```

###### The HTML `<span>` element is a generic inline container used to group content for styling purposes.
```html
<p>Add the <span>basil</span>, <span>pine nuts</span> and <span>garlic</span> to a blender and blend into a paste.</p>
<!-- Use <span> to give basil, pine nuts, and garlic different colors with CSS. -->
```
---

### `<hr>` Elements
###### The HTML `<hr>` element, horizontal rule element, represents a thematic break between sections of content.
```html
<h2>Ingredients</h2>
<hr>  <!-- Creates a horizontal line -->
<h2>Instructions</h2>
```
---

### `<br>` Elements
###### The HTML `<br>` element, line break element, produces a line break in text.
```html
<h2>Auguries of Innocence</h2>
<p>
    To see a World in a Grain of Sand<br>
    And a Heaven in a Wild Flower<br>
    Hold Infinity in the palm of your hand<br>
    And Eternity in an hour<br>
    A Robin Red breast in a Cage<br>
</p>
<!-- Useful with poems -->
```
---

### `<sub>` Elements
###### The HTML Subscript element `<sub>` displays inline text below the normal baseline, usually in smaller text.
```html
<p>I like H<sub>2</sub>O.</p>
<!-- Output: I like H₂O. -->

<!-- To display a fraction -->
 <p><sup>1</sup>/<sub>2</sub> + <sup>1</sup>/<sub>2</sub> = 1</p>
 <!-- Output: ½ + ½ = 1 -->
```
---

### `<sup>` Elements
###### The HTML Superscript element `<sup>` displays inline text above the normal baseline, usually in smaller text.
```html
<p>Chickens are primarily kept for their meat and eggs, though they are also kept as pets.<sup><a href="https://en.wikipedia.org/wiki/Chicken#cite_note-1">[1]</a></sup></p>
<!-- Output: Chickens are primarily kept for their meat and eggs, though they are also kept as pets.[¹] -->
```
---

### HTML Entities
###### HTML entities are special codes used to display characters that are reserved, difficult to type, or have special meaning in HTML.
- They start with `&` and end with `;`.
- The browser interprets them and displays the corresponding character.

```html
<!-- < and > are reserved characters in HTML, so use &lt; and &gt; to display them. -->
<p>5 &lt; 10 and 10 &gt; 5</p>
<!-- Output: 5 < 10 and 10 > 5 -->

<!-- Use a named entity or a numeric entity: &spades; or &#9824; -->
<p>Card suit: &#9824;</p>
<!-- Output: Card suit: ♠ -->
```
---

### Semantic Elements
###### Semantic Markup: Using HTML elements with specific names that describe the meaning and purpose of their content, rather than using generic elements like `<div>`.
```html
<section>    <!-- Represents a standalone section -->
<article>    <!-- Represents a self-contained piece of content -->
<nav>        <!-- Contains navigation links -->
<main>       <!-- Contains the main content of the document -->
<header>     <!-- Represents introductory content -->
<footer>     <!-- Represents footer content -->
<aside>      <!-- Represents content indirectly related to the main content --> 
<summary>    <!-- Provides a visible heading for <details> -->
<details>    <!-- Creates a disclosure widget that can be opened/closed -->
 
<time>       <!-- Represents a date or time -->
<figure>     <!-- Represents self-contained content, such as an image with a caption -->
<figcaption> <!-- Provides a caption for a <figure> -->
<abbr>       <!-- Represents an abbreviation -->
<data>       <!-- Associates content with a machine-readable value -->
``` 
---

### VS Code Tip: Emmet
###### Emmet: A tool built into VS Code that helps you write HTML faster. Some examples:
- Child elements: Use `>` to create nested elements.
```html
<!-- main>section>h1 and press Tab -->
<main>
  <section>
    <h1></h1>
  </section>
</main>
```

- Sibling elements: Use `+` to create elements at the same level.
```html
<!-- h1+h2+h3 and press Tab -->
<h1></h1>
<h2></h2>
<h3></h3>
```

- Multiplication: Use `*` to create multiple elements.
```html
<!-- ul>li*4 and press Tab -->
<ul>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
</ul>
```
---

## References
- *[The HTML Specification](https://html.spec.whatwg.org/)*
- *[Named Character References](https://html.spec.whatwg.org/multipage/named-characters.html)*
- *[Entity Code](https://entitycode.com/)*
- *[Stripe Marketing Page - Example of Semantic Elements](https://stripe.com/en-gr)*
- *[Emmet Documentation](https://docs.emmet.io/)*
