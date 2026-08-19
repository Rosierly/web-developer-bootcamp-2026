# Section 06 - CSS: The Very Basics

## Notes

### Conceptual Overview of CSS (**C**ascading **S**tyles **S**heet)
###### CSS is a language for describing how documents are presented visually - how they are arranged and styled.

#### Basic CSS Syntax - CSS Rules
```css
/* Almost everything you do in CSS follows this basic syntax */
selector {
    property: value;
}
```
#### Examples
```css
/* Make all <h1> elements purple. */
h1 {
    color: purple;
}

/* Make all image elements 100px wide & 200px tall */
img {
    width: 100px;
    height: 200px;
}
```
---

### Including Styles Correctly

#### Inline Styles
###### You can write styles directly inline on each element, but this is usually not recommended.
```html
<h1 style="color: purple">Hello World</h1>
<button style="background-color: palegreen">I am button</button>
<button style="background-color: palegreen">Another button</button>
<!-- Negative: Styles must be written separately on each element, making them difficult to reuse and maintain. -->
```

#### The `<style>` element
###### You can write styles inside a `<style>` element. This is simple, but the styles can’t be shared between documents.
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Intro</title>

    <style>
        h2 {
            color: pink;
        }
    </style>
</head>

<body>
    <!-- All <h2> elements share the same style -->
    <h2>I am an h2</h2>
    <h2>I am another h2</h2>
</body>

</html>
<!-- Negative: The styles cannot be easily reused across multiple pages. -->
```

#### External Stylesheet
###### You can write styles in a separate `.css` then include it using a `<link>` element in the `<head>` of your HTML document. This is the recommended approach.
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Intro</title>
    <link rel="stylesheet" href="styles.css">
</head>

<body>
    <h2>I am an h2</h2>
    <h2>I am another h2</h2>
</body>

</html>
```
```css
h2 {
    color: indigo;
}
```
---

### Basic & Common CSS Properties

#### Color Properties
| Property           | Definition                                                                            | Examples                           |
| ------------------ | ------------------------------------------------------------------------------------- | ---------------------------------- |
| `color`            | Sets the foreground, usually the text, color.                                         | `red`, `#ff0000`, `rgb(255, 0, 0)` |
| `background-color` | Sets the background color of an element.                                              | `blue`, `#000`, `rgb(0, 0, 0)`     |
| `background`       | Shorthand for background properties such as color, image, position, size, and repeat. | `background: red;`                 |

#### Text Properties
| Property          | Definition                                                                            | Examples                                                                                        |
| ----------------- | ------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| `text-align`      | Controls the **horizontal** alignment of text.                                        | `left`, `right`, `center`, `justify`                                                            |
| `font-family`     | Sets the font used for text. You can use **built-in/web-safe fonts**, custom fonts, and fallback fonts in priority order. Generic families such as `sans-serif` act as a final fallback and match any available font from that family.    | `Gill Sans Extrabold, Arial, sans-serif`                                                        |
| `font-size`       | Sets the size of the text.                                                            | `1.2em`, `x-small`, `smaller`, `12px`, `80%`                                                    |
| `font-weight`     | Controls the boldness of text. Available weights depend on the font.                  | `normal`, `bold`, `lighter`, `bolder`, `100–900`                                                |
| `text-decoration` | Controls decorative lines on text, such as underlines, overlines, and strikethroughs. | `underline`, `underline dotted`, `underline dotted red`, `underline wavy green`, `line-through` |
| `line-height`     | Controls the height of each line of text.                                             | `normal`, `2em`, `150%`, `32px`, `2.5`                                                          |
| `letter-spacing`  | Controls the spacing between characters. Negative values reduce the spacing.          | `normal`, `2em`, `1px`, `-1px`                                                                  |

#### Other Properties
| Property | Definition                     | Examples                        |
| -------- | ------------------------------ | ------------------------------- |
| `width`  | Sets the width of an element.  | `300px`, `50%`, `20rem`, `auto` |
| `height` | Sets the height of an element. | `200px`, `50%`, `20rem`, `auto` |
---

### Color Systems: Named Colors, RGB, & Hex
###### There are different ways to use CSS colors.

- #### Named Colors
    ###### Use a predefined color name.
    ```css
    p {
        color: indigo;
    }
    ```

- #### RGB System
    ###### RGB stands for Red, Green, and Blue. Each channel ranges from `0` to `255`.
    ```css
        p {
            color: rgb(0, 0, 0);  /* black */
            background-color: rgb(89, 151, 0);  /* olive green */
        }
    ```

- #### Hex (Hexadecimal)
    ###### Uses `#` followed by 6 hexadecimal characters: `#RRGGBB`. Each pair represents Red, Green, and Blue, with values from `00` to `ff` (`0–255`). Hex uses numbers `0–9` and letters `A–F`, where `A–F` represent values `10–15`.
    ```css
        p {
            color: #ffff00;  /*yellow*/
            /* #ffff00 → ff Red + ff Green + 00 Blue = yellow. */
        }
    ```
    **Note:** If both characters in each pair are the same, you can shorten the hex code to 3 characters.
    - `#000000` → `#000` → black
    - `#ffffff` → `#fff` → white
    - `cc55ee`  → `c5e`  → magenta
---

### CSS Size Units: Relative & Absolute

#### Relative Units
| Unit  | Definition                               |
| ----- | ---------------------------------------- |
| `em`  | Relative to the element's font size      |
| `rem` | Relative to the root (`html`) font size  |
| `vh`  | Relative to the viewport height          |
| `vw`  | Relative to the viewport width           |
| `%`   | Relative to a containing/reference value |

#### Absolute Units
| Unit | Definition                                   |
| ---- | -------------------------------------------- |
| `px` | CSS pixels; commonly used for precise sizing |
| `pt` | Points; `1pt = 1/72in`                       |
| `cm` | Centimeters                                  |
| `in` | Inches                                       |
| `mm` | Millimeters                                  |

**Note about `px`:**  
It's the most commonly used CSS unit. `1px` is a CSS pixel, not necessarily one physical screen pixel. Avoid relying too heavily on `px` for responsive layouts.

---

## References
- *[BookStore UI Codepen](https://codepen.io/TurkAysenur/pen/JjGKKrP)*
- *[MDN CSS Property Reference - List of All CSS Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)*
- *[Named Colors Reference](https://htmlcolorcodes.com/color-names/)*
- *[Color Picker](https://htmlcolorcodes.com/color-picker/)*
- *[CSS Font Stack Website](https://www.cssfontstack.com/)*
