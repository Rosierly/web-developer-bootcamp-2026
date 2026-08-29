# Section 10 - Responsive CSS & Flexbox

## Notes

### CSS Flexbox
###### Flexbox is a one-dimentional layout method for laying out items in rows or columns

Flexbox is a recent addition to CSS, that allows us to distrubute space dymamically across elements of an unknown size, hence the term "flex".

```html
<h1>Let's Play With Flexbox</h1>

<section id="container">
    <div style="background-color: #80ffdb"></div>
    <div style="background-color: #64dfdf"></div>
    <div style="background-color: #48bfe3"></div>
    <div style="background-color: #5390d9"></div>
    <div style="background-color: #6930c3"></div>
</section>
```
```css
#container {
    background-color: #003049;
    width: 90%;
    height: 500px;
    margin: 0 auto;
    border: 5px solid #003049;
    display: flex; /* turns the container into a flex container, laying items out in a row by default */
}

#container div {
    width: 200px;
}
```
---

### Flex-Direction
###### `flex-direction` determines the direction of the main axis and therefore how flex items are arranged inside a flex container.

Flexbox has two axes:
- Main axis — the direction items are laid out.
- Cross axis — perpendicular to the main axis.

```css
flex-direction: row; /* default: main axis runs horizontally */
flex-direction: row-reverse; /* reverses the direction of the horizontal main axis */
flex-direction: column; /* main axis runs vertically */
flex-direction: column-reverse; /* reverses the direction of the vertical main axis */
```
**Note:** 
- `row` / `column` → choose the main axis
- `-reverse` → reverse its direction
---

### Justify-Content
###### `justify-content` controls how flex items are aligned and distributed along the main axis.
```css
justify-content: flex-start; /* default */ 
justify-content: flex-end; /* moves items to the end of the main axis*/ 
justify-content: center; /* centers items along the main axis */ 
justify-content: space-between; /* equal space between items, none at the edges */ 
justify-content: space-around; /* equal space around each item; half-space at the edges */
justify-content: space-evenly; /* equal space between all items and edges */
```
**Note:** The main axis depends on `flex-direction`.

---

### Flex-wrap
###### `flex-wrap` determines whether flex items wrap onto a new line when they don't fit along the main axis.
```css
flex-wrap: nowrap; /* default: items stay on one line */ 
flex-wrap: wrap; /* items wrap onto new lines */ 
flex-wrap: wrap-reverse; /* items wrap in the opposite cross-axis direction */
```
---

### Align-Items
###### `align-items` controls how flex items are aligned along the cross axis.
```css
align-items: stretch; /* default: stretches items to fill the cross axis */ 
align-items: flex-start; /* aligns items at the start of the cross axis */ 
align-items: flex-end; /* aligns items at the end of the cross axis */ 
align-items: center; /* centers items along the cross axis */ 
align-items: baseline; /* aligns items by their text baselines */
```
**Note:** The cross axis depends on `flex-direction`.

---

### Align-Content & Align-Self

###### `align-content` controls how multiple flex lines (rows or columns) are distributed along the cross axis. It only has an effect when there are multiple lines, usually with `flex-wrap: wrap` or `flex-wrap: wrap-reverse`.
```css
align-content: stretch; /* default */
align-content: flex-start; /* lines at the start */ 
align-content: flex-end; /* lines at the end */ 
align-content: center; /* lines centered */ 
align-content: space-between; /* equal space between lines */ 
align-content: space-around; /* equal space around lines */ 
align-content: space-evenly; /* equal space between lines and edges */
```

###### `align-self` controls the alignment of one flex item along the cross axis, overriding the container's align-items value for that item.
```css
align-self: auto; /* default: uses the parent's/container's align-items value */
align-self: stretch; 
align-self: flex-start; 
align-self: flex-end; 
align-self: center; 
align-self: baseline; 
```
---

### Flex-Basis, Grow & Shrink
###### 
```css
```
---

### Flex Shorthand
######
```css
```
---


### Media Queries
######
```css
```
---
