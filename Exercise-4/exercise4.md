# Exercise 4 - Flexbox and Grid Layouts

## Introduction

In this exercise, you will learn about CSS Flexbox and Grid, two powerful layout systems that make it easy to create responsive, modern web layouts. These tools have revolutionized web design by providing flexible and intuitive ways to arrange content.

### Why Flexbox and Grid?

Before Flexbox and Grid, developers used floats, positioning, and inline-block elements for layouts, which were often complex and hacky. Modern CSS layout tools solve these problems:

- **Flexbox** (Flexible Box Layout) is ideal for **one-dimensional layouts** - arranging items in a row or column
- **CSS Grid** is perfect for **two-dimensional layouts** - creating complex layouts with rows and columns simultaneously

Both can be used together to create sophisticated, responsive designs!

---

## Part 1: Guided Steps - Flexbox

Flexbox is designed for laying out items in a single direction (either horizontally or vertically). It consists of a **flex container** (parent) and **flex items** (children).

### Understanding Flexbox Concepts

**Flex Container Properties** (applied to the parent):
- `display: flex` - Creates a flex container
- `flex-direction` - Defines the direction of items (row, column, row-reverse, column-reverse)
- `justify-content` - Aligns items along the main axis (horizontal if row, vertical if column)
- `align-items` - Aligns items along the cross axis (perpendicular to main axis)
- `flex-wrap` - Controls whether items wrap to new lines
- `gap` - Adds space between flex items

**Flex Item Properties** (applied to children):
- `flex-grow` - Determines how much an item grows relative to others
- `flex-shrink` - Determines how much an item shrinks relative to others
- `flex-basis` - Sets the initial size of an item
- `flex` - Shorthand for flex-grow, flex-shrink, and flex-basis
- `align-self` - Overrides align-items for a specific item

### Step 1: Creating a Basic Flex Container

Let's start with a simple horizontal layout.

**How to use:**
```css
.flex-container-basic {
    display: flex;
    background-color: #f0f0f0;
    padding: 10px;
}

.flex-item {
    background-color: #4CAF50;
    color: white;
    padding: 20px;
    margin: 5px;
}
```

**Explanation:**
- `display: flex` turns the container into a flex container
- By default, items are arranged in a **row** (horizontally)
- Items automatically adjust to fit the container

**Your task:**
1. Open `exercise4.html` in your code editor
2. In the `<style>` section, add the CSS above to style `.flex-container-basic` and `.flex-item`
3. Save and open the file in a browser to see the items arranged horizontally
4. Try adding `gap: 10px` to the flex container to add space between items

### Step 2: Changing Flex Direction

Flex direction controls whether items flow horizontally (row) or vertically (column).

**How to use:**
```css
.flex-container-column {
    display: flex;
    flex-direction: column;
    background-color: #e0e0e0;
    padding: 10px;
    margin-top: 20px;
}
```

**Explanation:**
- `flex-direction: row` (default) - Items arranged left to right
- `flex-direction: column` - Items arranged top to bottom
- `flex-direction: row-reverse` - Items arranged right to left
- `flex-direction: column-reverse` - Items arranged bottom to top

**Your task:**
1. Add the CSS above to style `.flex-container-column`
2. Observe how the items now stack vertically
3. Try changing `flex-direction` to `row-reverse` and see what happens

### Step 3: Aligning Items with Justify-Content

`justify-content` controls how items are distributed along the **main axis** (horizontal for row, vertical for column).

**How to use:**
```css
.flex-container-justify {
    display: flex;
    justify-content: space-between;
    background-color: #d0d0d0;
    padding: 10px;
    margin-top: 20px;
}
```

**Explanation:**
- `justify-content: flex-start` (default) - Items at the start
- `justify-content: flex-end` - Items at the end
- `justify-content: center` - Items centered
- `justify-content: space-between` - Items spread out, no space at edges
- `justify-content: space-around` - Items spread out, half space at edges
- `justify-content: space-evenly` - Items spread out, equal space everywhere

**Your task:**
1. Add the CSS above to style `.flex-container-justify`
2. Observe how items are distributed with space between them
3. Try changing `justify-content` to `center` and `space-evenly` to see the differences

### Step 4: Aligning Items with Align-Items

`align-items` controls how items are aligned along the **cross axis** (perpendicular to the main axis).

**How to use:**
```css
.flex-container-basic {
    display: flex;
    align-items: center;
    height: 150px;
    background-color: #f0f0f0;
    padding: 10px;
}
```

**Explanation:**
- `align-items: stretch` (default) - Items stretch to fill the container
- `align-items: flex-start` - Items aligned at the top
- `align-items: flex-end` - Items aligned at the bottom
- `align-items: center` - Items centered vertically
- `align-items: baseline` - Items aligned by their text baseline

**Your task:**
1. Update your `.flex-container-basic` CSS to include `align-items: center` and `height: 150px`
2. Observe how items are now vertically centered
3. Try changing `align-items` to `flex-end` to see items align at the bottom

### Step 5: Creating a Navigation Bar with Flexbox

Let's apply Flexbox to create a practical navigation bar.

**How to use:**
```css
.navbar {
    display: flex;
    justify-content: space-around;
    background-color: #333;
    padding: 15px;
    margin-top: 20px;
}

.navbar a {
    color: white;
    text-decoration: none;
    padding: 10px 20px;
    background-color: #555;
    border-radius: 5px;
    transition: background-color 0.3s;
}

.navbar a:hover {
    background-color: #4CAF50;
}
```

**Explanation:**
- The navbar uses Flexbox to distribute links evenly
- `justify-content: space-around` creates equal spacing
- The `:hover` effect makes the navbar interactive

**Your task:**
1. Add the CSS above to style the `.navbar`
2. Save and view in a browser
3. Hover over the navigation links to see the effect
4. Try changing `justify-content` to `flex-start` or `space-between` to see different layouts

### Step 6: Flexible Items with Flex-Grow

The `flex-grow` property controls how items grow to fill available space.

**How to use:**
```css
.flex-container-grow {
    display: flex;
    background-color: #c0c0c0;
    padding: 10px;
    margin-top: 20px;
}

.flex-item-grow-1 {
    flex-grow: 1;
    background-color: #2196F3;
    color: white;
    padding: 20px;
    margin: 5px;
}

.flex-item-grow-2 {
    flex-grow: 2;
    background-color: #f44336;
    color: white;
    padding: 20px;
    margin: 5px;
}
```

**Explanation:**
- `flex-grow: 1` means the item will take 1 part of available space
- `flex-grow: 2` means the item will take 2 parts (twice as much)
- Items without `flex-grow` (or `flex-grow: 0`) don't grow

**Your task:**
1. In the HTML, add a new div with class `flex-container-grow` after the navbar
2. Inside it, add three divs: two with class `flex-item-grow-1` and one with class `flex-item-grow-2`
3. Add the CSS above
4. Observe how the item with `flex-grow: 2` takes up more space

---

## Part 2: Guided Steps - CSS Grid

CSS Grid is a two-dimensional layout system that allows you to create complex layouts with rows and columns simultaneously. It provides precise control over layout in both directions.

### Understanding Grid Concepts

**Grid Container Properties** (applied to the parent):
- `display: grid` - Creates a grid container
- `grid-template-columns` - Defines column sizes
- `grid-template-rows` - Defines row sizes
- `grid-template-areas` - Names grid areas for easier layout
- `gap` or `grid-gap` - Adds space between grid items
- `justify-items` - Aligns items horizontally within their cells
- `align-items` - Aligns items vertically within their cells

**Grid Item Properties** (applied to children):
- `grid-column` - Specifies which columns an item spans
- `grid-row` - Specifies which rows an item spans
- `grid-area` - Assigns an item to a named grid area

### Step 1: Creating a Basic Grid

Let's create a simple 3-column grid.

**How to use:**
```css
.grid-container-basic {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 10px;
    background-color: #f0f0f0;
    padding: 10px;
    margin-top: 20px;
}

.grid-item {
    background-color: #FF9800;
    color: white;
    padding: 20px;
    text-align: center;
    font-size: 20px;
}
```

**Explanation:**
- `display: grid` creates a grid container
- `grid-template-columns: 1fr 1fr 1fr` creates 3 equal columns
- `fr` (fraction) unit divides available space proportionally
- `gap: 10px` adds spacing between grid items

**Alternative ways to define columns:**
```css
/* Three equal columns */
grid-template-columns: repeat(3, 1fr);

/* Fixed size columns */
grid-template-columns: 200px 200px 200px;

/* Mixed sizes */
grid-template-columns: 200px 1fr 2fr;
```

**Your task:**
1. Add the CSS above to style `.grid-container-basic` and `.grid-item`
2. Save and view in a browser - you should see a 3-column grid
3. Try changing `grid-template-columns` to `repeat(2, 1fr)` to create 2 columns
4. Try `grid-template-columns: 1fr 2fr 1fr` to make the middle column larger

### Step 2: Defining Rows and Columns

You can control both rows and columns in a grid.

**How to use:**
```css
.grid-container-rows {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: 100px 150px;
    gap: 10px;
    background-color: #e0e0e0;
    padding: 10px;
    margin-top: 20px;
}
```

**Explanation:**
- `grid-template-rows: 100px 150px` creates 2 rows with specific heights
- First row is 100px tall, second row is 150px tall
- If you have more items than rows defined, Grid auto-creates additional rows

**Your task:**
1. In the HTML, add a new div with class `grid-container-rows` after the basic grid
2. Inside it, add 6 divs with class `grid-item` and number them 1-6
3. Add the CSS above
4. Observe how the first 3 items are in the first row, next 3 in the second row

### Step 3: Spanning Multiple Columns or Rows

Grid items can span multiple columns or rows.

**How to use:**
```css
.grid-container-span {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
    background-color: #d0d0d0;
    padding: 10px;
    margin-top: 20px;
}

.grid-item-span {
    background-color: #9C27B0;
    color: white;
    padding: 20px;
    text-align: center;
}

.grid-item-wide {
    grid-column: span 2;
    background-color: #673AB7;
}

.grid-item-tall {
    grid-row: span 2;
    background-color: #3F51B5;
}
```

**Explanation:**
- `grid-column: span 2` makes an item span 2 columns
- `grid-row: span 2` makes an item span 2 rows
- You can also use `grid-column: 1 / 3` to span from column line 1 to 3

**Your task:**
1. In the HTML, add a new div with class `grid-container-span` after the rows grid
2. Inside it, add 5 divs with class `grid-item-span`
3. Give one div the additional class `grid-item-wide`
4. Add the CSS above and observe how the item spans 2 columns

### Step 4: Grid Template Areas

Grid template areas provide a visual way to define layouts using named areas.

**How to use:**
```css
.grid-container-layout {
    display: grid;
    grid-template-areas:
        "header header header"
        "sidebar content content"
        "footer footer footer";
    grid-template-columns: 200px 1fr 1fr;
    grid-template-rows: auto 1fr auto;
    gap: 10px;
    min-height: 400px;
    background-color: #c0c0c0;
    padding: 10px;
    margin-top: 20px;
}

.grid-header {
    grid-area: header;
    background-color: #333;
    color: white;
    padding: 20px;
    text-align: center;
}

.grid-sidebar {
    grid-area: sidebar;
    background-color: #555;
    color: white;
    padding: 20px;
}

.grid-content {
    grid-area: content;
    background-color: #f0f0f0;
    padding: 20px;
}

.grid-footer {
    grid-area: footer;
    background-color: #333;
    color: white;
    padding: 20px;
    text-align: center;
}
```

**Explanation:**
- `grid-template-areas` defines a visual layout using names
- Each string represents a row
- Each word in a string represents a column
- Repeating a name makes an item span multiple areas
- Items are assigned to areas using `grid-area`

This creates a classic website layout:
```
[  Header spanning full width  ]
[Sidebar][   Content area      ]
[  Footer spanning full width  ]
```

**Your task:**
1. Add the CSS above to style the grid layout that's already in the HTML
2. Save and view in a browser
3. You should see a complete page layout with header, sidebar, content, and footer
4. Try modifying the template areas to change the layout

### Step 5: Responsive Grid with Auto-Fit

Create a responsive grid that automatically adjusts the number of columns.

**How to use:**
```css
.grid-container-auto {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 15px;
    background-color: #b0b0b0;
    padding: 10px;
    margin-top: 20px;
}

.grid-item-auto {
    background-color: #00BCD4;
    color: white;
    padding: 30px;
    text-align: center;
}
```

**Explanation:**
- `repeat(auto-fit, minmax(200px, 1fr))` is powerful:
  - `auto-fit` automatically adjusts the number of columns
  - `minmax(200px, 1fr)` makes columns at least 200px, but grow to fill space
  - Grid automatically wraps items when space is limited
- This creates a fully responsive grid without media queries!

**Your task:**
1. In the HTML, add a new div with class `grid-container-auto` 
2. Inside it, add 8 divs with class `grid-item-auto` and number them 1-8
3. Add the CSS above
4. Resize your browser window and watch the grid automatically adjust columns

---

## Part 3: Partially Independent Tasks

Now that you've learned Flexbox and Grid basics, complete these tasks with less guidance.

### Task 1: Create a Card Layout with Flexbox

Create a section with a flex container that holds three card elements:
- Each card should have:
  - A heading (`<h3>`)
  - A paragraph with description
  - A button or link
  - Background color, padding, and border-radius for styling
- The cards should be displayed in a row with equal spacing
- Each card should grow to equal size using `flex: 1`
- Add hover effects to the cards (scale, shadow, or color change)

**Hints:**
- Use `display: flex` on the container
- Use `flex: 1` on the cards to make them equal width
- Use `gap` for spacing between cards
- Use `transition` for smooth hover effects

### Task 2: Create a Photo Gallery with Grid

Create a photo gallery section:
- Use CSS Grid with 4 columns on desktop
- Add at least 8 placeholder divs with background colors (simulating images)
- Make one item span 2 columns and 2 rows (featured item)
- Use `gap` for spacing between items
- Each item should have:
  - A minimum height of 200px
  - A background color
  - Centered text showing the item number

**Hints:**
- Use `display: grid`
- Use `grid-template-columns: repeat(4, 1fr)`
- Use `grid-column: span 2` and `grid-row: span 2` for the featured item
- Use `display: flex`, `justify-content: center`, and `align-items: center` inside each item to center text

### Task 3: Combine Flexbox and Grid

Create a dashboard layout that uses both Flexbox and Grid:
- Use Grid for the overall page layout (header, sidebar, main content, footer)
- Inside the main content area, use Flexbox to create a row of stat cards
- Each stat card should display:
  - A number (large text)
  - A label (small text)
  - An icon or symbol
- Use Flexbox within each card to arrange the content vertically and center it

**Hints:**
- Use `grid-template-areas` for the page structure
- Use Flexbox with `flex-direction: column` inside the stat cards
- Use `align-items: center` to center card content

### Task 4: Responsive Navigation

Create a responsive navigation bar using Flexbox:
- On larger screens, display links horizontally with space between them
- Include a logo on the left
- Include navigation links that align to the right
- Add a hover effect to the links
- Style it to look professional

**Hints:**
- Use `display: flex` with `justify-content: space-between`
- Group the navigation links in a div and use Flexbox on that as well
- Use `gap` for spacing between nav items

---

## Challenge Exercise: Responsive Card Gallery

Create a complete responsive card gallery that combines everything you've learned!

### Requirements:

1. **HTML Structure:**
   - Create a section with a heading "Featured Projects"
   - Add 6 project cards, each containing:
     - A colored background (simulating an image)
     - A project title
     - A short description
     - Tags (e.g., "HTML", "CSS", "JavaScript")
     - A "View Project" button

2. **Layout:**
   - Use CSS Grid for the overall card layout
   - Use Flexbox inside each card to arrange content vertically
   - Use Flexbox for the tags to display them horizontally

3. **Responsive Behavior:**
   - Desktop (>900px): 3 columns
   - Tablet (600px-900px): 2 columns
   - Mobile (<600px): 1 column
   - Use `grid-template-columns: repeat(auto-fit, minmax(300px, 1fr))` OR media queries

4. **Styling:**
   - Each card should have:
     - Border radius
     - Box shadow
     - Padding
     - Hover effect (lift up with transform or change shadow)
   - The colored background area should be at least 150px tall
   - Tags should be small with rounded borders
   - Button should be styled with hover effect

5. **Advanced (Optional):**
   - Make one card span 2 columns (featured project)
   - Add smooth transitions to all hover effects
   - Add a gradient background to the colored areas
   - Make tags different colors based on technology

### Example Solution Structure:

```html
<section id="challenge-section">
    <h2>Featured Projects</h2>
    <div class="card-gallery">
        <div class="card featured">
            <div class="card-image"></div>
            <div class="card-content">
                <h3>Project Title</h3>
                <p>Project description goes here...</p>
                <div class="tags">
                    <span class="tag">HTML</span>
                    <span class="tag">CSS</span>
                </div>
                <button class="card-button">View Project</button>
            </div>
        </div>
        <!-- More cards... -->
    </div>
</section>
```

**CSS Starter:**
```css
.card-gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
    padding: 20px;
}

.card {
    /* Add your styles here */
    display: flex;
    flex-direction: column;
}

.card-image {
    /* Add your styles here */
    height: 150px;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}

.card-content {
    /* Add your styles here */
    padding: 20px;
}

.tags {
    /* Use Flexbox to arrange tags horizontally */
    display: flex;
    gap: 10px;
}

/* Add more styles... */
```

Try to complete this challenge on your own, referring back to the earlier steps as needed!

---

## Summary

In this exercise, you learned:

✓ **Flexbox Basics:**
  - Creating flex containers with `display: flex`
  - Using `flex-direction` to control item flow
  - Aligning items with `justify-content` and `align-items`
  - Making flexible items with `flex-grow`
  - Creating practical layouts like navigation bars

✓ **CSS Grid Basics:**
  - Creating grid containers with `display: grid`
  - Defining columns and rows with `grid-template-columns` and `grid-template-rows`
  - Using `fr` units and `repeat()` for flexible grids
  - Spanning items across multiple columns/rows
  - Creating layouts with `grid-template-areas`
  - Making responsive grids with `auto-fit` and `minmax()`

✓ **When to Use Each:**
  - **Use Flexbox** for one-dimensional layouts (navigation bars, card rows, form inputs)
  - **Use Grid** for two-dimensional layouts (page layouts, galleries, dashboards)
  - **Combine both** for complex, nested layouts

✓ **Best Practices:**
  - Use semantic HTML elements (`<header>`, `<nav>`, `<main>`, `<footer>`)
  - Start with mobile-first design
  - Use `gap` instead of margins for spacing in Flex and Grid
  - Use relative units (`fr`, `%`, `em`) for responsive designs
  - Test your layouts at different screen sizes

## Additional Resources

To continue learning about Flexbox and Grid:
- [CSS-Tricks: A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [CSS-Tricks: A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Flexbox Froggy](https://flexboxfroggy.com/) - A game to learn Flexbox
- [Grid Garden](https://cssgridgarden.com/) - A game to learn CSS Grid
- [MDN Web Docs: Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout)
- [MDN Web Docs: CSS Grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)

## Tips

- **Flexbox** is your friend for components and simple one-directional layouts
- **Grid** excels at overall page structure and complex two-dimensional layouts
- Use browser DevTools to visualize and debug Flex and Grid layouts
- Don't be afraid to nest Flex containers inside Grid containers (and vice versa)
- The `gap` property works in both Flexbox and Grid - use it!
- Practice, practice, practice - layout is best learned by doing

Great job completing Exercise 4! You now have powerful tools for creating modern, responsive layouts. Keep practicing and experimenting with different combinations of Flexbox and Grid!

---

## Saving Your Work

After completing this exercise, make sure to save your changes to GitHub:

### Using VS Code (Recommended)

VS Code has a built-in Source Control panel that makes it easy to stage, commit, and push your changes:

1. **Open the Source Control panel**
   - Click the Source Control icon in the left sidebar (it looks like a branch symbol)
   - Or use the keyboard shortcut: `Ctrl+Shift+G` (Windows/Linux) or `Cmd+Shift+G` (Mac)

2. **Review your changes**
   - You'll see a list of files you've modified under "Changes"
   - Click on a file to see what you changed (green = added, red = removed)

3. **Stage your changes**
   - Hover over "Changes" and click the `+` button to stage all files
   - Or click the `+` button next to individual files to stage them one at a time

4. **Commit your changes**
   - Type a commit message in the text box at the top (e.g., "Completed Exercise 4 - Flexbox and Grid Layouts")
   - Click the checkmark button (✓) above the message box or press `Ctrl+Enter` (Windows/Linux) or `Cmd+Enter` (Mac)

5. **Push to GitHub**
   - Click the "Sync Changes" button that appears, or
   - Click the three dots menu (•••) and select "Push"

### Using Command Line (Alternative)

If you prefer using the terminal:

```bash
git add .
git commit -m "Completed Exercise 4 - Flexbox and Grid Layouts"
git push
```

Your work is now saved and backed up on GitHub! You can continue to the next exercise.
