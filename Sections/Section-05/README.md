# Section 05 - HTML: Forms & Tables

## Notes

### Tables in HTML
- #### What are tables?
    Tables are structured sets of data, made up of row and columns. They can be a great way of displaying data clearly.

- #### Early Usage
    In the early days of the web, tables were commonly used to create page layouts. Today, you should only use the table element when you are creating an actual data table.
---

### Table Basics: `<table>`, `<tr>`, `<td>` and `<th>`
###### HTML tables are used to organize and display tabular data in rows and columns.

- `<table>` → The idea that it represents tabular data organized into rows and columns.
- `<tr>` → Defines a row of cells and can contain <th> and <td>.
- `<td>` → Defines a data cell.
- `<th>` → Defines a header cell.

```html
<h1>Heaviest Birds</h1>

<table>
    <tr>
        <th>Animal</th>
        <th>Average mass
            [kg (lb)]</th>
        <th>Maximum mass
            [kg (lb)]</th>
        <th>Flighted</th>
    </tr>
    <!-- Each <tr> represents a new table row -->
    <tr>
        <td>Ostrich</td>
        <td>104 (230)</td>
        <td>156.8 (346)</td>
        <td>No</td>
    </tr>  
    <tr>
        <td>Somali Ostrich</td>
        <td>90 (200)</td>
        <td>130 (287)</td>
        <td>No</td>
    </tr>
</table>
```
---

### Table Sections: `<thead>`, `<tfoot>`, `<tbody>`
###### These elements divide a table into logical sections. They improve the semantic structure of the table and can also help with accessibility and styling.

- `<thead>` → Groups the header rows of a table.
- `<tbody>` → Groups the main data rows of a table.
- `<tfoot>` → Groups footer or summary rows of a table.

```html
<h1>Heaviest Birds</h1>

<table>
    <!-- A <thead> can contain more than one header row -->
    <thead>
        <tr>
            <th>Animal</th>
            <th>Average mass
                [kg (lb)]</th>
            <th>Maximum mass
                [kg (lb)]</th>
            <th>Flighted</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Ostrich</td>
            <td>104 (230)</td>
            <td>156.8 (346)</td>
            <td>No</td>
        </tr>  
        <tr>
            <td>Somali Ostrich</td>
            <td>90 (200)</td>
            <td>130 (287)</td>
            <td>No</td>
        </tr>
        <tr>
            <td>Wild Turkey</td>
            <td>13.5 (29.8)</td>
            <td>39 (86)</td>
            <td>Yes</td>
        </tr> 
    </tbody>
</table>
```
---

### Table Colspan and Rowspan
###### Attributes used to control how many columns or rows a table cell spans.

- `colspan` → Makes a cell span multiple columns.
- `rowspan` → Makes a cell span multiple rows.

```html
<h1>V2</h1>

<table>
    <thead>
        <tr>
            <th rowspan="2">Animal</th>
            <th colspan="2">Average Mass</th>
            <th rowspan="2">Flighted</th>
        </tr>
        <tr>
            <!-- These two headers sit underneath "Average Mass" -->
            <th>KG</th>
            <th>LB</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Ostrich</td>
            <td>104</td>
            <td>230</td>
            <td>No</td>
        </tr>  
        <tr>
            <td>Somali Ostrich</td>
            <td>90</td>
            <td>200</td>
            <td>No</td>
        </tr>
        <tr>
            <td>Wild Turkey</td>
            <td>13.5</td>
            <td>29.8</td>
            <td>Yes</td>
        </tr> 
    </tbody>
</table>
```
---

### Table Elements - Summary

| Element | Description |
|---|---|
| `<table>` | Defines the table itself. |
| `<tr>` | Defines a row in the table. |
| `<td>` | Defines a standard data cell. |
| `<th>` | Defines a header cell. |
| `<thead>` | Groups the header rows of a table. |
| `<tbody>` | Groups the main body rows of a table. |
| `<tfoot>` | Groups the footer rows of a table. |
| `<colgroup>` | Groups one or more columns for styling or formatting. |
| `<caption>` | Defines a title or description for the table. |

| Attribute | Description |
|---|---|
| `colspan` | Makes a cell span multiple columns. |
| `rowspan` | Makes a cell span multiple rows. |
---

### Form Element Basics
###### The `<form>` element is a container that doesn't have any visual impact. Used for interactive controls such as inputs, checkboxes, and buttons, and handles submitting their data.

- `action` → Specifies where the form data is sent.
- `method` → Specifies the HTTP method used to submit the form, typically `GET` or `POST`.

**Note:** When a form is submitted, an HTTP request is sent. The `action` attribute controls where that request is sent.

```html
<h1>Forms Demo</h1>

<form action="/tacos">
    <!-- Nothing will be visible on the webpage so far; we need to add content -->
</form>
```
---

### Common Input Types
###### The `<input>` element creates interactive form controls for accepting different types of data from users. We have 20+ possible types of inputs, ranging from date pickers to checkboxes.

- `type` → Specifies the type of input and determines its behavior and appearance.
- `placeholder` → Displays a temporary hint or example inside an input.

```html
<!-- The <input> element has no closing tag -->
<!-- If we don't specify the type attribute, it defaults to a text input -->

<h1>Forms Demo</h1>

<form action="/tacos">
    <input type="text" placeholder="username">          <!-- Accepts text input -->
    <input type="password" placeholder="password">      <!-- Accepts password text; characters are hidden/masked -->
    <input type="color">                                <!-- Opens a color picker -->
    <input type="number" placeholder="enter a number">  <!-- Accepts numeric input -->
    <input type="time">                                 <!-- Allows the user to select a time -->
</form>
```
---

### Labels
###### The `<label>` element provides a text description for a form control and can make the control clickable, improving usability and accessibility.

- `for` → Connects the label to an input by matching the input's `id`.
- `id` → Provides a unique identifier for the input that the label references.

```html
<h1>Forms Demo</h1>

<form action="/tacos">
    <p>
        <!-- The `for` attribute associates the label with the input's id -->
        <!-- Clicking the label focuses the associated input -->
        <label for="username">Enter a Username:</label>  
        <input id="username" type="text" placeholder="username">
    </p>
    <p>
        <label for="password">Enter a Password:</label> <!-- <label> is an inline element by default -->
        <input id="password" type="password" placeholder="password">
    </p>
    <p>
        <label for="color">Choose a Color:</label>
        <input id="color" type="color">
    </p>
    <!-- An alternative way to associate a label with an input is to nest the input inside the label (less common) -->
    <p>
        <label>
            Enter a Number:
            <input type="number" placeholder="enter a number">
            </label>
    </p>
</form>
```
---

### Button Elements
###### The `<button>` element creates a clickable button that can be used to submit forms or perform other actions.

- `type` → Specifies the button's behavior. Defaults to `submit` when used inside a form; can also be set to `button`.
- `value` → Sets the displayed text of an `<input type="submit">` button.

```html
<form action="/tacos">
    <!-- type="button" prevents the button from submitting the form -->
    <button type="button">Do Not Submit The Form</button>

    <!-- A <button> inside a form defaults to type="submit" -->
    <button>Submit</button>

    <!-- <input type="submit"> also creates a submit button -->
    <!-- The value attribute sets the button's displayed text -->
    <input type="submit" value="Click Me">
</form>

<!-- Outside of a form, a button does not submit a form -->
<button>Not Inside Form</button>
```
---

### The `name` Attribute
###### The `name` attribute gives a form control a name used to identify its data when the form is submitted; without it, the control's value is not included in the submitted form data.

```html
<form action="/tacos">
    <label for="username">Enter a Username:</label>
    <input id="username" type="text" placeholder="username" name="username">

    <label for="color">Choose a Color:</label>
    <input id="color" type="color" name="color">

    <button>Submit</button>
</form>
```

**Note:** With the default `GET` method, form data is sent in the URL as query parameters. With the `POST` method, form data is sent in the HTTP request body instead of the URL.

For example, if the user enters colt and selects #e21212
> /tacos?username=colt&color=%23e21212
- `username=colt` → `username` is the name and `colt` is the value entered by the user.
- `color=%23e21212` → `color` is the name and `%23e21212` is the encoded value of #e21212.
---

### Example: Search Reddit, Google, and YouTube Using a Form
###### We can use a form to send a search query directly to a website. The `action` attribute specifies the website's search URL, while the `name` attribute must match the query parameter that the website expects.

```html
<h2>Hijacking Searches</h2>

<h3>Search Reddit</h3>
<!-- Reddit expects the search query in a parameter named "q" -->
<form action="https://www.reddit.com/search">
    <input type="text" name="q">
    <button>Search Reddit</button>
</form>
<!-- https://www.reddit.com/search?q=cats -->

<h3>Search Google</h3>
<!-- Google expects the search query in a parameter named "q" -->
<form action="https://www.google.com/search">
    <input type="text" name="q"> 
    <button>Search Google</button>
</form>
<!-- https://www.google.com/search?q=cats -->

<h3>Search Youtube</h3>
<!-- YouTube expects the search query in a parameter named "search_query" -->
<form action="https://www.youtube.com/results">
    <input type="text" name="search_query">
    <button>Search Youtube</button>
</form>
<!-- https://www.youtube.com/results?search_query=cats -->
```
| Website | `action` | Search parameter |
|---|---|---|
| Reddit | `/search` | `q` |
| Google | `/search` | `q` |
| YouTube | `/results` | `search_query` |
---

### Radio Buttons, Checkboxes & Selects
###### Different types of the HTML `<input>` element and form controls.

#### Checkbox
###### A checkbox allows the user to select or deselect an option. Unlike radio buttons, multiple checkboxes can be selected at the same time. 

- By default, a checkbox is unchecked. You can use the checked attribute to make it `checked` when the page loads.

```html
<form action="/birds"> 
     <input type="checkbox" name="agree_tos" id="agree" checked>
     <label for="agree">I agree to everything</label> 
     <button>Submit</button> 
</form> 
<!-- file:///birds?agree_tos=on 
If the checkbox is NOT checked: file:///birds 
An unchecked checkbox is not included in the form submission at all. -->
```

#### Radio Buttons
###### Radio buttons allow the user to choose only one option from a group.

- To connect radio buttons into the same group, they must have the same `name` attribute.

- The `value` attribute specifies the value that is sent to the server when the form is submitted.

```html
<form action="/birds">
    <div>
        <label for="xs">XS:</label>
        <input type="radio" name="size" id="xs" value="xs">

        <label for="s">S:</label>
        <input type="radio" name="size" id="s" value="s">

        <label for="m">M:</label>
        <input type="radio" name="size" id="m" value="m">
    </div>

    <button>Submit</button>
</form>
<!-- file:///birds?size=m
 if you don't specify the value file:///birds?size=on -->
```

#### Selects
###### The `<select>` element creates a dropdown menu.

- `<select>` creates the dropdown.
- `<option>` creates the individual choices inside the dropdown.
- The value of the selected `<option>` is submitted with the form.

```html
<form action="/wedding">
    <div>
        <label for="meal">Please Select an Entree</label>
        <select name="meal" id="meal">
            <!-- Sometimes the first option is a placeholder. Giving it an empty value means that selecting it submits an empty value. -->
            <option value="">--Please choose an option--</option>
            <option value="fish">Fish</option>
            <option value="veg">Vegetarian</option>
            <!-- "selected" makes this option selected by default. -->
            <option value="steak" selected>Steak</option>
        </select>
    </div>
    <button>Submit</button>
</form>
<!-- file:///wedding?meal=steak -->
```
---

### Range & Text Areas
###### More types of form elements in HTML.

#### Range
###### `<input type="range">` lets the user select a number using a slider. Because this kind of widget is imprecise, it shouldn't typically be used unless the control's exact value isn't important.

- You can control the range with `min`, `max`, and `step`.

```html
    <form action="/birds">
        <p>
            <label for="cheese">Amount of Cheese</label>
            <input id="cheese" type="range" min="1" max="100" value="75" step="7" name="cheese_level">
            <!-- value = starting/default value -->
        </p>
        
        <button>Submit</button>
    </form>
<!-- file:///birds?cheese_level=75 -->
```

#### Number Type Input
###### You can also use `min`, `max`, and `step` with number input.

```html
    <form action="bird">
        <p>
            <label for="number">Enter a Number</label>
            <input type="number" placeholder="enter a number" name="num" min="0" max="1000" step="2">
            <!-- with `step="2": 0, 2, 4, 6, 8, 10...` -->
        </p>

        <button>Submit</button>
    </form>
```

#### Text Area
###### `<textarea>` lets the user enter multiple lines of text. It's useful for comments, feedback, messages, etc.

```html
<form action="/birds">
    <p>
        <label for="requests">Any Special Requests?</label>
        <br>
        <textarea id="requests" rows="10" cols="40" name="Requests?" placeholder="Type something here"></textarea>
        <!-- rows = initial height 
         cols = initial width -->
    </p>

    <button>Submit</button>
</form>
```
---

### Form Validations
###### Form validation means adding rules to check user input before it is submitted. 

For example:
- A field cannot be empty.
- A password must be between 12 and 20 characters.
- An email must have a valid format.

> HTML provides built-in browser validation, which happens before the form is submitted. Server-side validation can also be used to check the data after it is sent to the server.

#### HTML Attributes: `required`, `minlength` & `maxlength`

```html
<h2>Validations Demo</h2>
<form action="/dummy">
    <label for="first">Enter First Name</label>
    <input id="first" type="text" name="first" required>
    
    <p>
    <label for="username">Username</label>
    <input id="username" type="text" name="username" minlength="5" maxlength="20" required>
    </p>

    <button>Submit</button>
</form>
```

#### HTML Attributes: `pattern`
###### Some input types already have built-in validation. We can also create our own validation using the pattern attribute with a regular expression (regex).

```html
<form action="/dummy">
    <div>
        <input type="email" required>
        <!-- type="email" checks for a basic email format, such as something@something -->
        <input type="url">
        <!-- type="url" checks for a URL format, such as https://example.com -->
    </div>

    <button>Submit</button>
</form>
```
---

### Form Elements - Summary

#### Form

| Element / Attribute | Description                                                   |
| ------------------- | ------------------------------------------------------------- |
| `<form>`            | Container for form controls and submitted data.               |
| `action`            | Specifies where the form data is sent.                        |
| `method`            | Specifies how the form data is sent, usually `GET` or `POST`. |

#### Form Control Attributes

| Attribute     | Description                                   |
| ------------- | --------------------------------------------- |
| `name`        | Identifies the control's data when submitted. |
| `value`       | Defines the value of a form control.          |
| `id`          | Uniquely identifies an element.               |
| `placeholder` | Displays a temporary hint inside an input.    |


#### Input Types

| Input Type | Description                                             |
| ---------- | ------------------------------------------------------- |
| `text`     | Accepts text input.                                     |
| `password` | Accepts text while hiding the characters.               |
| `number`   | Accepts numeric input.                                  |
| `color`    | Opens a color picker.                                   |
| `time`     | Allows the user to select a time.                       |
| `range`    | Allows the user to select a number using a slider.      |
| `checkbox` | Allows one or multiple options to be selected.          |
| `radio`    | Allows one option to be selected from a group.          |
| `email`    | Accepts an email address and provides basic validation. |
| `url`      | Accepts a URL and provides basic validation.            |
| `submit`   | Creates a button for submitting a form.                 |

#### Labels

| Element / Attribute | Description                                |
| ------------------- | ------------------------------------------ |
| `<label>`           | Provides a description for a form control. |
| `for`               | Connects a label to an input's `id`.       |
| `id`                | Uniquely identifies an element.            |

#### Selection Controls

| Element / Attribute | Description                                    |
| ------------------- | ---------------------------------------------- |
| `<select>`          | Creates a dropdown menu.                       |
| `<option>`          | Creates an option inside a dropdown.           |
| `checked`           | Selects a checkbox or radio button by default. |
| `selected`          | Selects an option by default.                  |

#### Text Areas

| Element / Attribute | Description                      |
| ------------------- | -------------------------------- |
| `<textarea>`        | Creates a multi-line text input. |
| `rows`              | Sets the initial height.         |
| `cols`              | Sets the initial width.          |

#### Buttons

| Element / Attribute | Description                                                  |
| ------------------- | ------------------------------------------------------------ |
| `<button>`          | Creates a clickable button.                                  |
| `type`              | Defines the button's behavior, such as `submit` or `button`. |

#### Validation

| Attribute   | Description                                     |
| ----------- | ----------------------------------------------- |
| `required`  | Requires the user to enter a value.             |
| `minlength` | Sets the minimum number of characters.          |
| `maxlength` | Sets the maximum number of characters.          |
| `min`       | Sets the minimum allowed value.                 |
| `max`       | Sets the maximum allowed value.                 |
| `step`      | Sets the allowed increments for numeric inputs. |
| `pattern`   | Defines a custom validation rule using regex.   |
---

## References
- *[Wikipedia Table Example](https://en.wikipedia.org/wiki/List_of_largest_cities#List)*
- *[Dole/ Kemp 96 Website - Example of Using Tables to Structure a Website](https://www.dolekemp96.org/main.htm)*
- *[Wikipedia - Heaviest Living Bird Species Table](https://en.wikipedia.org/wiki/List_of_largest_birds#Table_of_heaviest_extant_bird_species)*
