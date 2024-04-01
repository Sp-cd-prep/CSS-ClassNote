## Class 1: Introduction to CSS and Text Formatting

### Part 1: Introduction to CSS

**Definition:**
CSS stands for Cascading Style Sheets. It is a language used to describe the presentation of web pages, including their layout, colors, fonts, and more. CSS allows you to control the visual appearance of HTML elements on a webpage.

**Implementation:**
CSS can be applied to HTML elements using three different methods: Inline, Internal, and External.

1. **Inline CSS:**
   Inline CSS is applied directly to an HTML element using the `style` attribute. It's useful for making small, specific style changes.

   ```html
   <p style="color: blue;">This is a blue text.</p>
   ```

2. **Internal CSS:**
   Internal CSS is placed within the `<style>` element in the HTML document's `<head>`. It affects elements throughout the document.

   ```html
   <head>
     <style>
       p {
         color: red;
       }
     </style>
   </head>
   ```

3. **External CSS:**
   External CSS is stored in a separate `.css` file and linked to the HTML document using the `<link>` element. This method is best for maintaining consistent styles across multiple pages.

   ```html
   <head>
     <link rel="stylesheet" type="text/css" href="styles.css" />
   </head>
   ```

### Part 2: Tags vs IDs vs Classes

**Tags:**
HTML tags represent different elements on a webpage, like headings (`<h1>`, `<h2>`, ...), paragraphs (`<p>`), links (`<a>`), etc. You can target these tags in your CSS to apply styles.

**IDs:**
An ID is a unique identifier given to an HTML element using the `id` attribute. IDs are used to target specific elements for styling and JavaScript interactions.

**Classes:**
A class is a reusable identifier applied to one or more HTML elements using the `class` attribute. Classes allow you to apply the same styles to multiple elements.

**Implementation:**

```html
<!DOCTYPE html>
<html>
  <head>
    <link rel="stylesheet" type="text/css" href="styles.css" />
  </head>
  <body>
    <h1>This is a heading</h1>
    <p id="unique-paragraph">This is a unique paragraph with an ID.</p>
    <p class="common-paragraph">This is a common paragraph with a class.</p>
  </body>
</html>
```

| Characteristic | Class                    | ID                      |
|----------------|--------------------------|-------------------------|
| Syntax         | .class-name              | #id-name                 |
| Selectivity    | Less specific            | More specific           |
| Usage          | Multiple elements        | Unique to one element   |
| Application    | Multiple instances       | Unique identifier      |
| Styling        | Shared styles among      | Specific styles for     |
|                | multiple elements        | one element             |
| JavaScript     | Can be used multiple      | Should be unique       |
|                | times in the document     | within the document     |
| Examples       | .button, .container      | #header, #footer        |



1. **Syntax:**
   - Class: Defined with a period (`.`) followed by the class name (e.g., `.button`).
   - ID: Defined with a hash (`#`) followed by the ID name (e.g., `#header`).

2. **Selectivity:**
   - Class: Less specific, applies to multiple elements with the same class.
   - ID: More specific, unique to a single element within the document.

3. **Usage:**
   - Class: Can be used for multiple elements throughout the document.
   - ID: Should be unique, used for a specific element on a page.

4. **Application:**
   - Class: Applied to multiple instances of elements that share common styles.
   - ID: Used for a unique identifier, typically for a specific element with distinctive styles or functionality.

5. **Styling:**
   - Class: Shared styles among multiple elements with the same class.
   - ID: Specific styles applied to a single element with a unique ID.

6. **JavaScript:**
   - Class: Can be used multiple times in the document, suitable for selecting and manipulating groups of elements.
   - ID: Should be unique within the document, commonly used when selecting a specific element for JavaScript interactions.

7. **Examples:**
   - Class: Examples include `.button`, `.container`, applied to multiple instances of buttons or containers.
   - ID: Examples include `#header`, `#footer`, used for unique elements like a header or footer.




### Part 3: CSS Text Formatting

1. **Color:**
   The `color` property is used to change the text color. Colors can be specified in various ways, such as color names, HEX codes, RGB values, etc.

   ```css
   p {
     color: blue;
   }
   ```

2. **Font Family:**
   The `font-family` property defines the typeface for text. You can specify multiple font families, and the browser will use the first available font.

   ```css
   body {
     font-family: Arial, sans-serif;
   }
   ```

3. **Font Style:**
   The `font-style` property is used to apply styles like italic or oblique to text.

   ```css
   em {
     font-style: italic;
   }
   ```

4. **Font Size:**
   The `font-size` property sets the size of the font. It can be specified in various units like pixels (`px`), ems (`em`), or percentages (`%`).

   ```css
   h1 {
     font-size: 24px;
   }
   ```

5. **Using Google Fonts:**
   Google Fonts provides a wide range of free, web-safe fonts that you can use in your projects. To use Google Fonts, you need to link to the font stylesheet in your HTML.

   ```html
   <head>
     <link
       rel="stylesheet"
       href="https://fonts.googleapis.com/css?family=Roboto"
     />
   </head>
   ```

   ```css
   body {
     font-family: "Roboto", sans-serif;
   }
   ```

**Notes:**

- CSS is used to style HTML elements.
- There are three ways to apply CSS: Inline, Internal, and External.
- Tags, IDs, and Classes are used to target specific elements for styling.
- You can format text using properties like color, font family, font style, and font size.
- Google Fonts provides a wide variety of fonts for web use.


## CSS `background` Property Components and Values

### 1. `background-attachment`

This property specifies whether the background image scrolls with the content or remains fixed.

**Possible Values:**

- `scroll`: The background image scrolls with the content.
- `fixed`: The background image remains fixed in place.
- `local`: The background image scrolls with the element's content, ignoring the parent element's scrolling.

**Example:**

```css
.element {
  background-image: url("image.jpg");
  background-attachment: fixed;
}
```

**Example for all:**

```html
<p class="border-box">The background extends behind the border.</p>
<p class="padding-box">
  The background extends to the inside edge of the border.
</p>
<p class="content-box">
  The background extends only to the edge of the content box.
</p>
<p class="text">The background is clipped to the foreground text.</p>
```

```css
p {
  border: 0.8em darkviolet;
  border-style: dashed;
  margin: 1em 0;
  padding: 1.4em;
  background: linear-gradient(60deg, red, yellow, red, yellow, red);
  font: 900 1.2em sans-serif;
  text-decoration: underline;
}

.border-box {
  background-clip: border-box;
}
.padding-box {
  background-clip: padding-box;
}
.content-box {
  background-clip: content-box;
}

.text {
  background-clip: text;
  -webkit-background-clip: text;
  color: rgba(0, 0, 0, 0.2);
}
```

### 2. `background-clip`

This property determines the portion of the background that should be visible based on the element's padding box, border box, or content box.

**Possible Values:**

- `border-box`: The background extends beneath the border.
- `padding-box`: The background extends beneath the padding.
- `content-box`: The background is confined to the content area.

**Example:**

```css
.element {
  background-color: #f2f2f2;
  background-clip: padding-box;
}
```

### 3. `background-color`

This property sets the background color of an element.

**Possible Values:**

- Any valid color value (e.g., color names, HEX codes, RGB values, etc.).

**Example:**

```css
.element {
  background-color: lightblue;
}
```

### 4. `background-image`

This property specifies one or more background images for the element.

**Possible Values:**

- `none`: No background image.
- URL to an image file.

**Example:**

```css
.element {
  background-image: url("pattern.png");
}
```

### 5. `background-origin`

This property defines the origin of the background positioning area.

**Possible Values:**

- `border-box`: Origin is the border box.
- `padding-box`: Origin is the padding box.
- `content-box`: Origin is the content box.

**Example:**

```css
.element {
  background-image: url("image.jpg");
  background-origin: padding-box;
}
```

### 6. `background-position`

This property sets the initial position of the background image(s).

**Possible Values:**

- Keywords: `top`, `bottom`, `left`, `right`, `center`
- Percentages: Relative to the element's size.
- Length values: In pixels, ems, rems, etc.

**Example:**

```css
.element {
  background-image: url("image.jpg");
  background-position: right bottom;
}
```

### 7. `background-repeat`

This property determines how the background image(s) should repeat or not repeat.

**Possible Values:**

- `repeat`: Repeat both horizontally and vertically.
- `repeat-x`: Repeat only horizontally.
- `repeat-y`: Repeat only vertically.
- `no-repeat`: Do not repeat.
- `space`: Repeat as much as possible without clipping, adding space between images.

**Example:**

```css
.element {
  background-image: url("pattern.png");
  background-repeat: no-repeat;
}
```

### 8. `background-size`

This property specifies the size of the background image(s).

**Possible Values:**

- `auto`: Default size of the image.
- `cover`: Resize the image to cover the entire element while maintaining aspect ratio.
- `contain`: Resize the image to fit inside the element while maintaining aspect ratio.
- Length values: In pixels, ems, rems, etc.

**Example:**

```css
.element {
  background-image: url("image.jpg");
  background-size: cover;
}
```

The `background-size` property in CSS is used to control the size of the background image within an element. Here's an explanation of the differences between `cover`, `contain`, and `100%`:

1. **`background-size: cover;`**

   When you set `background-size: cover;`, the background image is scaled to cover the entire content area of the element while maintaining its aspect ratio. This means that the image will be enlarged (if necessary) to completely cover the element, potentially cropping parts of the image if it doesn't fit exactly.
   Basically It maksure that the image will cover all the parts of the element, no gaps are there, but sometimes the image will cropout.

   Example:

   ```css
   .element {
     background-image: url("image.jpg");
     background-size: cover;
   }
   ```

2. **`background-size: contain;`**

   With `background-size: contain;`, the background image is scaled to fit within the element's content area while also maintaining its aspect ratio. This ensures that the entire image is visible, and it might leave empty space around the image if the aspect ratios don't match.

   Example:

   ```css
   .element {
     background-image: url("image.jpg");
     background-size: contain;
   }
   ```

3. **`background-size: 100%;`**

   Setting `background-size: 100%;` means that the background image will be scaled to completely cover the element's content area, regardless of its original aspect ratio. This can lead to the image being stretched or distorted if its proportions are not the same as the element's proportions.

   Example:

   ```css
   .element {
     background-image: url("image.jpg");
     background-size: 100%;
   }
   ```

In summary:

- `cover` ensures the image covers the entire element's content area, potentially cropping parts.
- `contain` scales the image to fit within the element's content area while showing the whole image.
- `100%` scales the image to cover the whole content area, without necessarily maintaining the image's aspect ratio.


## CSS Box Model

The CSS Box Model describes the layout and rendering of elements in a web page. It consists of four main parts:

1. **Content:** The actual content of the element, such as text, images, or other media.
2. **Padding:** Space between the content and the border.
3. **Border:** A line that surrounds the padding and content.
4. **Margin:** Space outside the border, between the element and other elements.

### Content

- **`width`**: Specifies the width of the content area.
  - Value: Length (e.g., `px`, `em`, `%`), auto.
- **`height`**: Specifies the height of the content area.
  - Value: Length (e.g., `px`, `em`, `%`), auto.

### Padding

- **`padding-top`**, **`padding-right`**, **`padding-bottom`**, **`padding-left`**: Specifies the padding on each side of the element.
  - Value: Length (e.g., `px`, `em`, `%`), auto.
- **`padding`**: Shorthand for setting all padding sides simultaneously.
  - Value: Length (e.g., `px`, `em`, `%`), auto.

### Border

- **`border-width`**: Specifies the width of the border.
  - Value: Length (e.g., `px`, `em`, `%`).
- **`border-style`**: Specifies the style of the border.
  - Values: `none`, `hidden`, `dotted`, `dashed`, `solid`, `double`, `groove`, `ridge`, `inset`, `outset`.
- **`border-color`**: Specifies the color of the border.
  - Value: Color name, hex code, RGB, RGBA.
- **`border`**: Shorthand for setting border width, style, and color simultaneously.
  - Value: Width, style, color.

Certainly! Let's go through each CSS property with explanations and examples.

### `border-collapse`

- **Explanation**: Determines whether table borders should be collapsed into a single border or separated as distinct borders.
- **Values**: 
  - `collapse`: Borders are collapsed into a single border.
  - `separate`: Borders are displayed separately for each cell.
  
**Example**:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
        }
        th, td {
            border: 1px solid black;
            padding: 8px;
            text-align: left;
        }
    </style>
    <title>border-collapse Example</title>
</head>
<body>
    <table>
        <tr>
            <th>Header 1</th>
            <th>Header 2</th>
        </tr>
        <tr>
            <td>Cell 1</td>
            <td>Cell 2</td>
        </tr>
        <tr>
            <td>Cell 3</td>
            <td>Cell 4</td>
        </tr>
    </table>
</body>
</html>
```

In this example, `border-collapse: collapse;` is applied to the `<table>` element. This collapses the borders between cells into a single border. The `<th>` and `<td>` elements have a `border: 1px solid black;` style applied to create the cell borders.

### `border-radius`

- **Explanation**: Specifies the radius of the corners of an element's border.
- **Values**: Length value, percentage value, multiple values for individual corners (top-left, top-right, bottom-right, bottom-left).

**Example**:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        .box {
            width: 200px;
            height: 200px;
            background-color: lightblue;
            border: 2px solid black;
            border-radius: 20px; /* Applies same radius to all corners */
        }
    </style>
    <title>border-radius Example</title>
</head>
<body>
    <div class="box"></div>
</body>
</html>
```

In this example, `.box` is a `<div>` element styled with a width and height of 200px, a light blue background, and a black border with a width of 2px. The `border-radius: 20px;` property creates rounded corners for the border with a radius of 20 pixels on all four corners.

### `border-spacing`

- **Explanation**: Specifies the distance between the borders of adjacent cells in a table.
- **Values**: Length value or multiple length values for horizontal and vertical spacing.

**Example**:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        table {
            border-collapse: separate;
            border-spacing: 10px 5px; /* Horizontal spacing: 10px, Vertical spacing: 5px */
        }
        th, td {
            border: 1px solid black;
            padding: 8px;
            text-align: left;
        }
    </style>
    <title>border-spacing Example</title>
</head>
<body>
    <table>
        <tr>
            <th>Header 1</th>
            <th>Header 2</th>
        </tr>
        <tr>
            <td>Cell 1</td>
            <td>Cell 2</td>
        </tr>
        <tr>
            <td>Cell 3</td>
            <td>Cell 4</td>
        </tr>
    </table>
</body>
</html>
```

In this example, `border-collapse: separate;` is applied to the `<table>` element to display borders separately for each cell. `border-spacing: 10px 5px;` sets the horizontal spacing between cell borders to 10 pixels and the vertical spacing to 5 pixels. This creates space between adjacent cells in the table.



### Margin

- **`margin-top`**, **`margin-right`**, **`margin-bottom`**, **`margin-left`**: Specifies the margin on each side of the element.
  - Value: Length (e.g., `px`, `em`, `%`), auto.

The margin shorthand property in CSS allows you to set all four margins (top, right, bottom, and left) in a single declaration. Here's the syntax and explanation of the margin shorthand property:

### Syntax
```css
margin: [top] [right] [bottom] [left];
```

You can define the margin values in different ways:

### Example

```css
/* One value */
.element {
    margin: 10px; /* All margins set to 10px */
}

/* Two values */
.element {
    margin: 10px 20px; /* Top and bottom margins set to 10px, right and left margins set to 20px */
}

/* Three values */
.element {
    margin: 10px 20px 30px; /* Top margin set to 10px, right and left margins set to 20px, bottom margin set to 30px */
}

/* Four values */
.element {
    margin: 10px 20px 30px 40px; /* Top margin set to 10px, right margin set to 20px, bottom margin set to 30px, left margin set to 40px */
}
```


## Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        .box {
            width: 200px;
            height: 200px;
            padding: 20px;
            border-width: 2px;
            border-style: solid;
            border-color: black;
            margin: 20px;
        }
    </style>
    <title>CSS Box Model Example</title>
</head>
<body>
    <div class="box">
        This is the content.
    </div>
</body>
</html>
```



| Margin                                             | Padding                                      |
|----------------------------------------------------|----------------------------------------------|
| Margin provides the space between the border and nearby elements.   | Padding provides the space between the border and the content of the element.    |
| It is the space outside of the border       | it is the space inside the space the border.         |
| You can set margin values to be negative if you want element to overlap. | padding value can only be positive. |
| When you set the margin values the element size doesnot change, only the space arong it. | When you set padding values, the size of that element increses. |
                                       


