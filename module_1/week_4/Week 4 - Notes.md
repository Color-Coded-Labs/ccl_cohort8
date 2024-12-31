# HTML
## What is HTML?

HTML (Hypertext Markup Language) is the standard markup language for documents
designed to be displayed in a web browser. It helps structure the content and
present it on the web.

## Why Should I Learn HTML?

HTML is the backbone of web pages. Learning HTML is essential for anyone
interested in web development or design, as it's the basic building block for
creating websites.

## Document Structure

An HTML document follows a specific structure that includes various elements for
organizing and presenting content. Here's an expanded explanation of each
element:

- **`<!DOCTYPE html>`**: This declaration specifies the document type and
  version of HTML being used. It ensures that the browser renders the document
  correctly.

- **`<html>`**: The `<html>` element serves as the root element of the HTML
  document. It contains all the other elements and represents the entire content
  of the webpage.

- **`<head>`**: The `<head>` element is a container for meta-information about
  the document. It doesn't directly display any content on the webpage but
  includes elements like `<title>`, `<meta>`, and `<link>`. Here are some
  commonly used elements within the `<head>` section:

  - **`<title>`**: The `<title>` element sets the title of the webpage, which
    appears in the browser's title bar or tab.

    ```html
    <head>
      <title>My Web Page</title>
    </head>
    ```

  - **`<meta>`**: The `<meta>` element provides metadata about the HTML
    document. It includes information such as character encoding, author,
    description, keywords, and viewport settings. Here's an example of a
    viewport meta tag:

    ```html
    <head>
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    </head>
    ```

    The above `<meta>` tag sets the initial scale and width of the webpage to
    match the device's screen width.

- **`<body>`**: The `<body>` element contains the visible content of the
  webpage, such as text, images, links, and other HTML elements. It represents
  the main content area that users see and interact with.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My Web Page</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  </head>
  <body>
    <!-- Visible content goes here -->
  </body>
</html>
```

## Inline vs Block Elements

HTML elements can be categorized as either inline or block elements, each with
different rendering and layout behavior. Here are more examples of commonly used
inline and block elements:

**Inline Elements**: Inline elements do not start on a new line and only occupy
as much width as necessary.

- `<span>`: The `<span>` element is an inline container used to group inline
  elements and apply styles or scripts to specific sections of text.

```html
This is an <span>inline</span> element.
```

- `<a>`: The `<a>` element creates a hyperlink to another webpage or a specific
  location within the same webpage.

```html
Visit our <a href="https://www.example.com">website</a> for more information.
```

**Block Elements**: Block elements start on a new line and occupy the full width
available.

- `<div>`: The `<div>` element is a generic container used to group and style
  other HTML elements.

```html
<div>This is a block element.</div>
```

- `<h1>` to `<h6>`: Heading elements represent section headings of different
  levels, with `<h1>` being the highest and `<h6>` being the lowest.

```html
<h1>Main Heading</h1>
<h2>Subheading</h2>
```

- `<p>`: The `<p>` element represents a paragraph of text.

```html
<p>This is a paragraph.</p>
```

**Block Elements:**

- `<div>`
- `<p>`
- `<h1>` to `<h6>`
- `<ul>` (unordered list)
- `<ol>` (ordered list)
- `<li>` (list item)
- `<table>`
- `<tr>` (table row)
- `<td>` (table cell)
- `<th>` (table header cell)
- `<form>`
- `<blockquote>`
- `<pre>`
- `<address>`
- `<header>`
- `<nav>`
- `<main>`
- `<article>`
- `<section>`
- `<aside>`
- `<footer>`
- `<figure>`
- `<figcaption>`
- `<fieldset>`

**Inline Elements:**

- `<span>`
- `<a>`
- `<strong>` or `<b>` (bold text)
- `<em>` or `<i>` (italicized text)
- `<code>`
- `<time>` (date or time)
- `<img>`
- `<input>`
- `<label>`
- `<button>`
- `<select>`
- `<option>`
- `<textarea>`

## Semantic HTML

Semantic HTML elements provide meaning and structure to the content, making it
more understandable for both humans and machines. They convey the purpose and
role of different sections of a webpage. Here are seven examples of semantic
HTML elements:

- `<header>`: Represents the introductory content at the top of a webpage or a
  section.
- `<nav>`: Defines a section of navigation links.
- `<article>`: Represents an independent, self-contained piece of content, such
  as a blog post or news article.
- `<section>`: Represents a standalone section of content.
- `<aside>`: Defines content that is tangentially related to the main content,
  such as sidebars or pull quotes.
- `<footer>`: Represents the footer or closing section of a webpage or a
  section.
- `<main>`: Defines the main content area of the document.

Here's an example that demonstrates the usage of these semantic elements
together:

```html
<header>
  <h1>Website Title</h1>
  <nav>
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>
</header>

<main>
  <article>
    <header>
      <h2>Article Title</h2>
    </header>
    <section>
      <p>Content of the article...</p>
    </section>
    <footer>
      <p>Article footer.</p>
    </footer>
  </article>

  <aside>
    <h3>Related Articles</h3>
    <ul>
      <li><a href="#">Article 1</a></li>
      <li><a href="#">Article 2</a></li>
      <li><a href="#">Article 3</a></li>
    </ul>
  </aside>
</main>

<footer>
  <p>&copy; 2023 My Website. All rights reserved.</p>
</footer>
```

## Headings and Paragraphs

Headings and paragraphs are fundamental building blocks of any web page.
Headings are used to define the structure and layout of your content. Paragraphs
are used for regular text.

HTML headings are defined with the `<h1>` to `<h6>` tags, with `<h1>` being the
largest and `<h6>` the smallest.

```html
<h1>This is a heading level 1</h1>
<h2>This is a heading level 2</h2>
<h3>This is a heading level 3</h3>
<p>This is a paragraph.</p>
```

### Lists

There are two types of lists in HTML: unordered lists and ordered lists. An
unordered list is a collection of items that do not have a numerical order. This
is created using the `<ul>` element. An ordered list is a collection of items
that are numbered in order. This is created using the `<ol>` element.

```html
<!-- Unordered list -->
<ul>
  <li>Apple</li>
  <li>Banana</li>
  <li>Cherry</li>
</ul>

<!-- Ordered list -->
<ol>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ol>
```

## Images

The `<img>` tag is used to embed images in a document. The `src` attribute
contains the image URL and is mandatory. The `alt` attribute provides
alternative text for the image if it cannot be displayed.

```html
<img src="url-of-your-image.jpg" alt="Description of the image" />
```

## Links

Links are used to navigate between pages on the internet. The `<a>` tag is used
to create hyperlinks.

Basic link example:

```html
<a href="path-to-file.html">This is a link</a>
```

Open link in a new tab:

```html
<a href="https://example.com" target="_blank">Open in new tab</a>
```

## Forms and Inputs

Forms are essential for collecting data from the user. The `<form>` element is
used to create a form, and within this, various input elements and buttons can
be placed.

**Text Input**: For general text input.

```html
<input type="text" name="username" placeholder="Enter your username" />
```

**Password Input**: For password entry fields. Characters are obscured.

```html
<input type="password" name="password" placeholder="Enter your password" />
```

**Radio Buttons**: Let the user select one option from a set.

```html
<input type="radio" name="gender" value="male" /> Male
<input type="radio" name="gender" value="female" /> Female
```

**Checkboxes**: Allow the user to select multiple options.

```html
<input type="checkbox" name="option1" value="Option 1" /> Option 1
<input type="checkbox" name="option2" value="Option 2" /> Option 2
```

**Submit Button**: Used to submit a form.

```html
<input type="submit" value="Submit" />
```

**Email Input**: For email addresses.

```html
<input type="email" name="email" placeholder="Enter your email" />
```

**Number Input**: For numeric input.

```html
<input type="number" name="quantity" min="1" max="10" />
```

**Date Input**: For date input.

```html
<input type="date" name="birthday" />
```

## Labels

The `<label>` element is an essential part of forms. It is used to add text next
to an input element, improving usability and accessibility. The `for` attribute
in the `<label>` should have the same value as the `id` attribute of the input
it's associated with. This allows users to click the label to focus/select the
input element.

Here's how you can use the `<label>` element in conjunction with different input
types:

```html
<!-- Text input with label -->
<label for="username">Username:</label>
<input
  type="text"
  id="username"
  name="username"
  placeholder="Enter your username"
/>

<!-- Password input with label -->
<label for="password">Password:</label>
<input
  type="password"
  id="password"
  name="password"
  placeholder="Enter your password"
/>

<!-- Radio buttons with labels -->
<label for="male">Male</label>
<input type="radio" id="male" name="gender" value="male" />
<label for="female">Female</label>
<input type="radio" id="female" name="gender" value="female" />

<!-- Checkbox with label -->
<label for="option1">Option 1</label>
<input type="checkbox" id="option1" name="option1" value="Option 1" />

<!-- Number input with label -->
<label for="quantity">Quantity (between 1 and 10):</label>
<input type="number" id="quantity" name="quantity" min="1" max="10" />
```

Using labels not only makes the form more user-friendly but also makes it more
accessible to screen readers, improving the overall accessibility of your
webpage.

## Tables

Tables are used to organize data into rows and columns. They are created using
the `<table>` element.

```html
<table>
  <tr>
    <th>Header 1</th>
    <th>Header 2</th>
  </tr>
  <tr>
    <td>Row 1, Cell 1</td>
    <td>Row 1, Cell 2</td>
  </tr>
  <tr>
    <td>Row 2, Cell 1</td>
    <td>Row 2, Cell 2</td>
  </tr>
</table>
```

Here, `<tr>` defines a table row, `<th>` defines a header cell, and `<td>`
defines a standard cell in the table. This table is used to represent data in a
structured format, which can be particularly useful for displaying tabular data
like schedules, statistics, or lists.

---
# CSS

## What is CSS?

CSS (Cascading Style Sheets) is a stylesheet language used to describe the
presentation of a document written in HTML. It allows you to control the layout,
colors, fonts, and other visual aspects of web pages.

## Why Should I Learn CSS?

CSS is essential for web development because it provides the styling and
aesthetic aspects of a webpage. It makes websites visually appealing and
improves the user experience.

## How to Apply Styles

**Inline**: Directly within an HTML element using the `style` attribute.

```html
<p style="color: red;">This is an inline style.</p>
```

**Internal**: Within the `<style>` tags in the HTML `<head>` section.

```html
<head>
  <style>
    p {
      color: blue;
    }
  </style>
</head>
```

**External**: In a separate .css file that is linked to the HTML file.

```html
<link rel="stylesheet" href="styles.css" />
```

## Selectors

Selectors are patterns that match against elements in an HTML document, used to
apply styles.

**Type Selector**: Matches elements by node name.

    ```css
    p {
      color: green;
    }
    ```

**Class Selector**: Matches elements by class attribute.

    ```css
    .highlight {
      font-weight: bold;
    }
    ```

**ID Selector**: Matches a single element by its ID attribute.

    ```css
    #navbar {
      background-color: black;
    }
    ```

**Specificity**: Determines which CSS rule is applied when multiple rules could
apply to an element. It is calculated based on the different categories of
selectors.

- Inline styles have the highest specificity.
- ID selectors have higher specificity than class selectors.
- Class selectors have higher specificity than type selectors.

### Common CSS Properties

**Color**: Sets the text color.

```css
p {
  color: red;
}
```

**Text Alignment**: Aligns the text within an element.

```css
h1 {
  text-align: center;
}
```

**Font Size and Family**: Sets the font size and type for text.

```css
.text {
  font-size: 16px;
  font-family: Arial, sans-serif;
}
```

**Height and Width**: Sets the height and width of an element.

```css
.box {
  height: 100px;
  width: 200px;
}
```

**Border and Border Radius**: Sets the border style and radius (rounded
corners).

```css
.rounded-border {
  border: 2px solid blue;
  border-radius: 10px;
}
```

## Box Model

The CSS Box Model is the foundation of layout on the Web — each element is
represented as a rectangular box, with the box's content, padding, border, and
margin built up around one another like the layers of an onion.

- **Content**: The actual content of the box, where text and images appear.
- **Padding**: Clears an area around the content inside the border. It's
  transparent.
- **Border**: A border that goes around the padding and content.
- **Margin**: Clears an area outside the border.

Use padding when you want to create space within the element, and margin when
you want to create space between different elements.

```css
.div {
  content: "content";
  padding: 10px;
  border: 2px solid black;
  margin: 20px;
}
```

# Utilizing Flexbox in CSS to Arrange Elements

Flexbox is a CSS layout model that allows for a more efficient way to lay out, align, and distribute space among items in a container.

## Introduction to Flexbox

- **Flex Container**: To use Flexbox, first declare a container as a flex container with `display: flex;`.
- **Flex Items**: Elements inside the flex container become flex items.

    ```css
    .container {
        display: flex;
    }
    ```

## Properties of Flexbox

### For the Flex Container

- **flex-direction**: Defines the direction items are placed in the container (e.g., row, column).
- **justify-content**: Aligns items horizontally and distributes space.
- **align-items**: Aligns items vertically.

    ```css
    .container {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
    }
    ```

### For the Flex Items

- **flex-grow**: Defines the ability for an item to grow if necessary.
- **flex-shrink**: Defines the ability for an item to shrink if necessary.
- **flex-basis**: Defines the default size of an element before the remaining space is distributed.

    ```css
    .item {
        flex-grow: 1;
        flex-shrink: 0;
        flex-basis: 100px;
    }
    ```

## Using Flexbox for Layout

Flexbox is ideal for creating complex layouts with less code and more flexibility. It's especially useful for aligning elements, both vertically and horizontally, and for creating responsive designs.

# Creating and Styling HTML Forms

Forms are crucial in web interaction, allowing users to enter data that can be sent to a server for processing.

## Basic HTML Form Structure

- **Form Element**: The container for form elements.
- **Input Elements**: Text fields, radio buttons, checkboxes, etc.

    ```html
    <form action="/submit-form" method="post">
        <label for="name">Name:</label>
        <input type="text" id="name" name="name">
        
        <label for="email">Email:</label>
        <input type="email" id="email" name="email">

        <input type="submit" value="Submit">
    </form>
    ```

## Styling Forms with CSS

- Use CSS to style the form elements for a better user experience.
- Adjust margins, padding, borders, colors, and fonts to make the form intuitive and visually appealing.

    ```css
    form {
        margin: 20px 0;
    }
    
    label, input {
        margin: 10px 0;
        display: block;
    }
    ```

