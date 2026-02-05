# Exercise 2 - CSS Box Model

## Introduction

In this exercise, you will practice using the CSS box model to create layouts and style elements.

## Understanding the Box Model

The CSS box model is a fundamental concept that describes how elements are rendered on a web page. Every HTML element is represented as a rectangular box, and the box model defines the structure of this box.

### Box Model Components

The box model consists of four main areas (from inside to outside):

1. **Content**: The actual content of the element (text, images, etc.). The width and height properties set the size of this area.

2. **Padding**: The space between the content and the border. Padding is transparent and adds space inside the element. You can set padding for all sides at once or individually (padding-top, padding-right, padding-bottom, padding-left).

3. **Border**: A line that surrounds the padding and content. You can style the border with properties like border-width, border-style, and border-color.

4. **Margin**: The space outside the border. Margins are transparent and create space between elements. Like padding, you can set margins for all sides or individually.

### Visualizing the Box Model

```
+------------------------------------------+
|              Margin (transparent)         |
|  +------------------------------------+  |
|  |         Border                     |  |
|  |  +------------------------------+  |  |
|  |  |      Padding (transparent)   |  |  |
|  |  |  +------------------------+  |  |  |
|  |  |  |       Content          |  |  |  |
|  |  |  |     (width x height)   |  |  |  |
|  |  |  +------------------------+  |  |  |
|  |  +------------------------------+  |  |
|  +------------------------------------+  |
+------------------------------------------+
```

### Box-Sizing Property

By default, when you set width and height on an element, you're only setting the size of the content area. Any padding or border is added on top of that width/height.

- **content-box (default)**: Width and height apply only to the content. Total width = width + padding + border
- **border-box**: Width and height include padding and border. Total width = width (which already includes padding and border)

Example:
```css
/* Default behavior (content-box) */
.box1 {
    width: 300px;
    padding: 20px;
    border: 5px solid black;
    /* Total width = 300 + 40 (padding) + 10 (border) = 350px */
}

/* Border-box behavior */
.box2 {
    box-sizing: border-box;
    width: 300px;
    padding: 20px;
    border: 5px solid black;
    /* Total width = 300px (padding and border are included) */
}
```

## Instructions

### Part 1: Box Model Basics

1. Open the `exercise2.html` file in your code editor.
2. Create a `styles.css` file and link it to the `exercise2.html` file.
3. Add the following styles to the `styles.css` file:

    - Set the `box-sizing` property to `border-box` for all elements using the universal selector (`*`).
    - Style the `.box` class with:
      - Width of `300px`
      - Height of `200px`
      - Background color of `#e8f4f8`
      - Border of `3px solid #2c3e50`
      - Padding of `20px`
      - Margin of `20px`
    - Style the header `h1` element with:
      - Background color of `#2c3e50`
      - Text color of `#ecf0f1`
      - Padding of `20px`
      - Margin of `0`
    - Style the `section` element with:
      - Background color of `#f9f9f9`
      - Padding of `15px`
      - Margin of `20px 0`
      - Border of `2px solid #ddd`

4. Save the changes and open the `exercise2.html` file in a web browser to view the styled elements.
5. **Observe**: Open your browser's developer tools (F12) and inspect the `.box` element. Look at the box model visualization to see how padding, border, and margin create space around the content.

### Part 1.5: Experimenting with Box-Sizing

1. Add a new class called `.content-box-demo` in your `styles.css`:
    - Width: `300px`
    - Padding: `30px`
    - Border: `5px solid #e74c3c`
    - Background color: `#ffeaa7`
    - Margin: `10px`
    - Box-sizing: `content-box` (explicitly set the default)

2. Add another class called `.border-box-demo`:
    - Width: `300px`
    - Padding: `30px`
    - Border: `5px solid #00b894`
    - Background color: `#dfe6e9`
    - Margin: `10px`
    - Box-sizing: `border-box`

3. In the HTML file, add two new div elements inside the section (after the existing `.box` element) with these classes to see the difference.
4. **Question to ponder**: Why do these boxes have different total widths even though both have `width: 300px`?

### Part 2: Understanding Margin Collapse

1. Add a new section to your HTML file with two paragraphs.
2. Style both paragraphs with:
    - Margin-top: `30px`
    - Margin-bottom: `30px`
    - Background color: `#74b9ff`
    - Padding: `15px`

3. **Observe**: The space between the two paragraphs is NOT 60px (30px + 30px), but only 30px! This is called "margin collapse" - when vertical margins of adjacent elements meet, they collapse into a single margin equal to the larger of the two.
4. Try adding a border or padding to the parent section to prevent margin collapse and see the difference.

### Part 3: Layout Exercise

1. Create a new `div` element with a class of `container` inside the body (after the first section).
2. Add the following styles to the `container` class:

    - Max-width: `1000px`
    - Margin: `0 auto` (this centers the container)
    - Background color: `#f5f5f5`
    - Padding: `20px`
    - Border: `2px solid #ccc`

3. Inside the `container` div, create two `div` elements with classes `sidebar` and `content`.
4. Add the following styles to the `sidebar` class:

    - Width: `25%`
    - Background color: `#34495e`
    - Color: `#ecf0f1`
    - Padding: `15px`
    - Margin-right: `20px`
    - Float: `left` (or use display: inline-block)
    - Border-radius: `5px`

5. Add the following styles to the `content` class:

    - Width: `calc(75% - 20px)` (75% minus the margin-right of sidebar)
    - Background color: `#ffffff`
    - Color: `#2c3e50`
    - Padding: `15px`
    - Float: `left`
    - Border-radius: `5px`
    - Box-shadow: `0 2px 4px rgba(0,0,0,0.1)`

6. Don't forget to clear the floats! Add a `clearfix` after the container content or use `overflow: auto` on the container.
7. Save the changes and open the `exercise2.html` file in a web browser to view the styled layout.

### Additional Challenges

1. **Experiment with different values** for padding, margin, border-width, and width to see how they affect the total size of elements. Use the browser's developer tools to inspect the box model.

2. **Create a card component** with:
   - A fixed width of 250px
   - Padding of 20px
   - A border of 1px solid #ddd
   - Box-shadow for depth: `0 4px 6px rgba(0,0,0,0.1)`
   - Border-radius of 8px
   - Margin to space multiple cards apart

3. **Add hover effects** to your boxes that change padding, margin, or border-width. Notice how these changes affect the layout and can cause "jumps" in the page.

4. **Create a navigation bar** using the box model:
   - Set list items as inline-block
   - Add padding to create clickable areas
   - Add margin to space items apart
   - Add border-bottom on hover

5. **Practice responsive spacing**: Create a section that uses percentage-based widths and padding to maintain proportions at different screen sizes.

## Key Takeaways

- The box model determines how much space an element occupies on the page
- `box-sizing: border-box` makes sizing elements more intuitive by including padding and border in the width/height
- Padding creates internal spacing, margins create external spacing
- Vertical margins collapse between adjacent block elements
- Use browser developer tools to visualize and debug the box model
- Understanding the box model is essential for creating precise layouts and avoiding unexpected spacing issues

## Common Pitfalls

1. **Forgetting about box-sizing**: Without `border-box`, adding padding or borders increases the total element size
2. **Margin collapse**: Vertical margins between adjacent elements collapse to the larger value
3. **Horizontal overflow**: Elements with width + padding + border + margin exceeding container width will overflow
4. **Percentage calculations**: When using percentages, remember they're calculated from the parent element's content width
