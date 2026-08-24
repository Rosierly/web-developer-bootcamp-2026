# Section 9 - Other Assorted Useful CSS Properties

## Notes

### Opacity & Alpha Channel
###### Both opacity and alpha control transparency in CSS, but they do so at different levels.

- Alpha channel controls the transparency of a color. It is commonly used with `rgba()`, and 8-digit hexadecimal colors.
- `opacity` is a CSS property that controls the transparency of an entire element, including its background, text, borders, and child elements.

```css
/* Alpha channel — only the background color is transparent */
#rgba {
    background-color: rgba(0, 209, 112, 0.5);  /* alpha: 0 to 1 */

    /* Alternative: hex code — last two digits control transparency, from 00 to FF */
    background-color: #00D17080;
}

/* Opacity — the entire element becomes transparent */
#opacity {
    background-color: yellow;
    opacity: 0.5;  /* opacity: 0 to 1 */
}
```
---

### Position Property
###### The `position` CSS prorepty sets how an element is positioned in a document. The `top`, `right`, `bottom` and `left` properties determine the final location of positioned elements.

- `static` — Default position. Follows the normal document flow.
- `relative` — Moves the element relative to its original position.
- `absolute` — Positions the element relative to its nearest positioned ancestor. The parent/ancestor must have a position other than `static`. Otherwise, relative to the page.
- `fixed` — Positions the element relative to the viewport and stays there when scrolling.
- `sticky` — Moves normally until a specified position is reached, then stays there while scrolling.

```html
<h1>Position Property</h1>

<section id="static">
    <h2>Static</h2>
    <div></div>
    <div id="middle"></div>
    <div></div>
</section>

<section id="relative">
    <h2>Relative</h2>
    <div></div>
    <div id="middle"></div>
    <div></div>
</section>

<section id="absolute">
    <h2>Absolute</h2>
    <div></div>
    <div id="middle"></div>
    <div></div>
</section>

<section id="fixed">
    <h2>Fixed</h2>
    <div></div>
    <div id="middle"></div>
    <div></div>
</section>
```
```css
div {
    width: 100px;
    height: 100px;
    background-color: #3d405b;
    border: 2px solid black;
    margin: 10px;
    display: inline-block;
}

#middle {
    background-color: #81b29a;
}

#static #middle {
    position: static;
    top: 100px; /* Has no effect because the element is statically positioned */
}

#relative #middle {
    position: relative; /* The element stays in the normal flow, but can now be offset */
    top: 100px;
    left: 50px;
}

#absolute #middle {
    position: absolute;
    top: 100px;
    left: 50px; /* Offset from the nearest positioned ancestor */
}

#fixed #middle {
    position: fixed; 
    top: 100px;
    left: 0px; /* Positioned 100px from the top and 0px from the left of the viewport */
}
```
---

### Transitions
###### Transitions allow us to smoothly animate a property's value from one state to another.

A transition can specify:
- `property` — the property to animate
- `duration` — how long the transition takes
- `timing function` — controls the speed/pace of the transition
- `delay` — how long to wait before the transition starts (default: 0s)

> **Syntax**:  
> transition: property duration timing-function delay;

#### Transitioning Multiple Properties
```css
.circle {
    width: 300px;
    height: 300px;
    background-color: magenta;
    border-radius: 0;

    transition: background-color 2s 1s, border-radius 2s;
    /* background-color takes 2 seconds and has a 1-second delay.
       border-radius takes 2 seconds with no delay. */
}

.circle:hover {
    background-color: cyan;
    border-radius: 50%;
}

/* =========================================================== */

.circle {
    transition: all 2s;  /* use `all` to transition every animatable property that changes */
}
/* This is equivalent to: */
.circle {
    transition: 2s;
}

/* The second version uses the default property (all), duration (2s), timing function (ease), and delay (0s).

Note: Avoid using `transition: all` when possible. It can cause unexpected animations if you later add or change other properties. */
```

#### Transition Timing Functions
```css
section div {
    height: 100px;
    width: 100px;
    background-color: turquoise;
    margin: 20px 0;
    transition: margin-left 3s;
}

section:hover div {
    margin-left: 500px;
}

section div:nth-of-type(1) {
    transition-timing-function: ease-in;
}

section div:nth-of-type(2) {
    transition-timing-function: ease-out;
}

section div:nth-of-type(3) {
    transition-timing-function: cubic-bezier(0.7, 0, 0.84, 0);
}

section div:nth-of-type(4) {
    transition-timing-function: cubic-bezier(0.85, 0, 0.15, 1);
} /* cubic-bezier() allows you to create a custom timing curve */

/* Common timing functions include:
ease
ease-in
ease-out
ease-in-out
linear
cubic-bezier(...) */
```
**Note:** Check out References to see visual examples of different timing functions and how they affect animations.

---

### Transforms
###### The `transform` property lets you modify the appearance and position of an element without affecting the normal document layout.

Possible values:
- `translate()` — moves an element.
- `rotate()` — rotates an element.
- `scale()` — increases or decreases an element's size.
- `skew()` — slants an element (tilts an element at an angle).
- `matrix()` — combines multiple transformations.

`transform-origin` — sets the point around which a transformation is applied. The default is the center of the element.

```css
section:first-of-type h1:nth-of-type(1) {
    transform-origin: bottom right;

    transform: rotate(45deg);

    transform: scale(0.5);

    transform: translate(-100px, 50px);

    transform: skew(30deg);

    margin: 20px auto; /* centers an element in its container */
    /* margin: top & bottom left & right */
}
    /* margin: 0 auto; only centers an element horizontally when the element has a width smaller than its containing element. */
    

section:first-of-type h1:nth-of-type(2) {
    /* Multiple transformations can be combined by separating them with spaces */
    transform: translateX(-500px) rotate(0.5turn) scaleY(1.5);
}
```

**Note:** `transform` applies to the element it is used on, including its contents. If it is applied to a parent element, the parent and its contents are visually transformed together. For example, if a `section` contains an `h1` and a `button`, transforming the `section` visually transforms both the `section` and its contents together.

---

### Background Property - How To Set Background Images
###### The `background` property is a shorthand property for setting multiple background-related properties in a single declaration.

There are multiple background properties:
- `background-image` — sets one or more background images.
- `background-size` — controls the size of the background image.
- `background-position` — controls where the background image is - `positioned.
- `background-repeat` — controls whether the background image repeats.
- `background-color` — sets the background color.

#### `background-image`
```css
section {
    width: 80%;
    height: 800px;
    margin: 0 auto;

    background-image: url("image-url");
    background-size: cover;
    background-position: bottom;
    /* Starts displaying the image from the bottom. */
}
```

#### Using the `background` shorthand
```css
/* Instead of writing the properties separately, we can combine them using background: */
section {
    background: bottom/cover url("image-url");
}
```
**Note:** The order of most `background` values does not matter. However, when using `background-size` together with `background-position`, the size must come immediately after the position and be separated by `/`.
```css
section { 
    background: center/80% url("image-url");
}
/* center → background-position
80% → background-size
url(...) → background-image */
```

#### Multiple backgrounds
```css
/* We can also apply multiple background layers to the same element by separating them with commas. */
section {
    background: center/40% no-repeat url("image-url"), blueviolet;  /* Instead of a color, we can add another background image. */
}
```
---

### Google Fonts
###### Google Fonts is a free library of fonts that can be added to a website and used through CSS.

Copy the `<link>` from Google Fonts into the HTML `<head>`, then use the font with `font-family` in CSS.

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="styles.css">
</head>
```
```css
body {
    font-family: "Roboto", sans-serif;
}
```
---

## References
- *[Transition Easing Functions Website](https://easings.net/)*
- *[Unsplash - Free Stock Images](https://unsplash.com/)*
- *[Google Fonts Website](https://fonts.google.com/)*
