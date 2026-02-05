# Exercise 1 - CSS Basics and Styling

## Introduction

In this exercise, you will learn the fundamentals of CSS (Cascading Style Sheets) and practice styling HTML elements. CSS is what makes websites look beautiful by controlling colors, fonts, spacing, and visual effects.

**What is CSS?**
CSS stands for Cascading Style Sheets. It's a language used to describe how HTML elements should be displayed on screen. CSS separates the presentation (how things look) from the structure (HTML content).

**Why use CSS?**
- Makes websites visually appealing
- Creates consistent styling across multiple pages
- Separates content from design
- Makes websites easier to maintain

**Note:** This exercise focuses on **styling properties** (colors, fonts, borders, shadows, etc.). We will NOT cover layout properties (positioning, flexbox, grid) - those will be covered in Exercise 2.

---

## Understanding CSS Syntax

CSS consists of **rules** that target HTML elements. Each rule has two parts:

```css
selector {
    property: value;
    property: value;
}
```

- **Selector** - Specifies which HTML element(s) to style
- **Property** - What aspect to style (e.g., color, font-size)
- **Value** - How to style it (e.g., red, 16px)

**Example:**
```css
h1 {
    color: blue;
    font-size: 32px;
}
```

This rule targets all `<h1>` elements and makes them blue with a font size of 32 pixels.

---

## Three Ways to Add CSS

### 1. Internal CSS (Inside `<style>` tags)
```html
<head>
    <style>
        h1 { color: blue; }
    </style>
</head>
```

### 2. External CSS (Separate file)
```html
<head>
    <link rel="stylesheet" href="styles.css">
</head>
```

### 3. Inline CSS (Directly on elements) - Not recommended
```html
<h1 style="color: blue;">Heading</h1>
```

**Best practice:** Use external stylesheets for most projects as they keep your code organized and reusable.

---

## Part 1: Guided Steps - Basic CSS Properties

### Step 1: Setting Up Internal Styles

First, we'll practice using internal CSS before moving to external stylesheets.

**Your task:**
1. Open `exercise1.html` in your code editor
2. Inside the `<head>` element, add a `<style>` element
3. We'll add CSS rules inside this `<style>` element in the following steps

### Step 2: Colors

CSS offers multiple ways to define colors:
- **Named colors**: `red`, `blue`, `green` (140 color names available)
- **Hex codes**: `#ff0000` (red), `#0000ff` (blue)
- **RGB**: `rgb(255, 0, 0)` (red)
- **RGBA**: `rgba(255, 0, 0, 0.5)` (red with 50% opacity)

**Properties:**
- `color` - Text color
- `background-color` - Background color
- `opacity` - Transparency (0.0 to 1.0)

**Your task:**
1. Style the `h1` element:
   - Set `color` to `#2c3e50` (dark blue-gray)
   - Set `background-color` to `#ecf0f1` (light gray)
2. Style all `h2` elements:
   - Set `color` to `#34495e` (medium blue-gray)
3. Style the `body` element:
   - Set `background-color` to `#ffffff` (white)
   - Set `color` to `#333333` (dark gray text)

### Step 3: Typography - Font Properties

Typography is crucial for readability and visual appeal.

**Properties:**
- `font-family` - The typeface (e.g., Arial, Times New Roman)
- `font-size` - Size of text (px, em, rem, %)
- `font-weight` - Thickness of text (normal, bold, 100-900)
- `font-style` - Style of text (normal, italic, oblique)
- `line-height` - Vertical spacing between lines
- `letter-spacing` - Space between characters
- `word-spacing` - Space between words

**Common font stacks (fallback fonts):**
```css
font-family: Arial, Helvetica, sans-serif;
font-family: "Times New Roman", Times, serif;
font-family: Georgia, serif;
font-family: "Courier New", monospace;
```

**Your task:**
1. Style the `body` element:
   - Set `font-family` to `Arial, Helvetica, sans-serif`
   - Set `font-size` to `16px`
   - Set `line-height` to `1.6` (1.6 times the font size)
2. Style the `h1` element:
   - Set `font-size` to `36px`
   - Set `font-weight` to `bold`
   - Set `letter-spacing` to `1px`
3. Style the `h2` element:
   - Set `font-size` to `28px`
   - Set `font-weight` to `600`

### Step 4: Text Formatting

Control how text appears and aligns.

**Properties:**
- `text-align` - Alignment (left, right, center, justify)
- `text-decoration` - Underline, overline, line-through, none
- `text-transform` - Change case (uppercase, lowercase, capitalize)
- `text-indent` - Indent first line of text

**Your task:**
1. Style the `h1` element:
   - Set `text-align` to `center`
2. Style elements with class `intro`:
   - Set `text-align` to `center`
   - Set `font-style` to `italic`
3. Style elements with class `uppercase`:
   - Set `text-transform` to `uppercase`

### Step 5: Working with Links

Links have multiple states that can be styled differently.

**Link pseudo-classes:**
- `:link` - Unvisited link
- `:visited` - Visited link
- `:hover` - Mouse over link
- `:active` - Link being clicked

**Order matters!** Always define in this order: LVHA (Link, Visited, Hover, Active)

**Your task:**
1. Style all `a` elements:
   - Set `color` to `#3498db` (blue)
   - Set `text-decoration` to `none`
   - Set `font-weight` to `bold`
2. Style `a:hover` (when hovering over links):
   - Set `color` to `#2980b9` (darker blue)
   - Set `text-decoration` to `underline`
3. Style `a:visited`:
   - Set `color` to `#9b59b6` (purple)

### Step 6: Borders and Border Radius

Borders can be added to any element to create visual boundaries.

**Border properties:**
- `border` - Shorthand: `width style color` (e.g., `1px solid black`)
- `border-width` - Thickness (thin, medium, thick, or px value)
- `border-style` - Style (solid, dashed, dotted, double, none)
- `border-color` - Color of border
- `border-radius` - Rounds corners (px or %)

You can also style individual sides:
- `border-top`, `border-right`, `border-bottom`, `border-left`
- `border-top-left-radius`, `border-top-right-radius`, etc.

**Your task:**
1. Style elements with class `box`:
   - Set `border` to `2px solid #bdc3c7`
   - Set `border-radius` to `10px`
   - Set `background-color` to `#ecf0f1`
2. Style elements with class `card`:
   - Set `border` to `1px solid #ddd`
   - Set `border-radius` to `8px`
   - Set `border-left` to `4px solid #3498db`

### Step 7: Shadows

Shadows add depth and visual interest to elements.

**Shadow properties:**
- `box-shadow` - Shadow around elements: `x-offset y-offset blur spread color`
- `text-shadow` - Shadow on text: `x-offset y-offset blur color`

**Example:**
```css
box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.3);
/* 2px right, 2px down, 5px blur, 30% black */

text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
```

**Your task:**
1. Style elements with class `card`:
   - Set `box-shadow` to `0 2px 8px rgba(0, 0, 0, 0.1)`
2. Style the `h1` element:
   - Set `text-shadow` to `2px 2px 4px rgba(0, 0, 0, 0.2)`

### Step 8: List Styling

Control how lists appear.

**Properties:**
- `list-style-type` - Bullet/number style (disc, circle, square, decimal, none)
- `list-style-position` - Inside or outside (inside, outside)
- `list-style` - Shorthand for all list properties

**Your task:**
1. Style all `ul` elements:
   - Set `list-style-type` to `square`
2. Style elements with class `no-bullets`:
   - Set `list-style-type` to `none`
3. Style all `ol` elements:
   - Set `list-style-type` to `decimal`

---

## Part 2: Advanced Selectors

CSS offers powerful ways to target specific elements.

### Type 1: Class and ID Selectors

**Class selector** (can be used on multiple elements):
```css
.my-class { color: red; }
```

**ID selector** (should be unique on page):
```css
#my-id { color: blue; }
```

**Your task:**
1. Create a CSS rule for class `highlight`:
   - Set `background-color` to `#fff9c4` (light yellow)
   - Set `border-left` to `3px solid #f9a825`
2. Create a CSS rule for ID `footer`:
   - Set `background-color` to `#2c3e50`
   - Set `color` to `#ffffff`
   - Set `text-align` to `center`

### Type 2: Descendant and Child Selectors

**Descendant selector** (space) - Selects all descendants:
```css
div p { color: red; } /* All p elements inside div */
```

**Child selector** (>) - Selects direct children only:
```css
div > p { color: blue; } /* Only direct p children of div */
```

**Your task:**
1. Create a rule for `ul li`:
   - Set `color` to `#555`
2. Create a rule for `.box > p`:
   - Set `font-weight` to `bold`

### Type 3: Pseudo-classes

Pseudo-classes target elements in specific states.

**Common pseudo-classes:**
- `:first-child` - First child element
- `:last-child` - Last child element
- `:nth-child(n)` - Nth child element (e.g., 2n for even, 2n+1 for odd)
- `:hover` - Element being hovered over
- `:focus` - Element with focus (e.g., input fields)

**Your task:**
1. Style `li:first-child`:
   - Set `font-weight` to `bold`
   - Set `color` to `#2980b9`
2. Style `li:last-child`:
   - Set `font-style` to `italic`
3. Style `li:nth-child(even)`:
   - Set `background-color` to `#f5f5f5`

### Type 4: Pseudo-elements

Pseudo-elements style specific parts of elements.

**Common pseudo-elements:**
- `::before` - Insert content before element
- `::after` - Insert content after element
- `::first-letter` - First letter of text
- `::first-line` - First line of text

**Note:** Use double colons (::) for pseudo-elements, single colon (:) for pseudo-classes.

**Your task:**
1. Style `.card::before`:
   - Set `content` to `"💡 "` (lightbulb emoji with space)
2. Style `p::first-letter` inside elements with class `dropcap`:
   - Set `font-size` to `2em`
   - Set `font-weight` to `bold`
   - Set `color` to `#3498db`

---

## Part 3: Moving to External Stylesheet

Now that you've practiced with internal styles, let's move to a more professional approach.

**Your task:**
1. Create a new file named `styles.css` in the Exercise-1 folder
2. Copy all CSS rules from inside the `<style>` tags to the `styles.css` file
3. Remove the `<style>` element from `exercise1.html`
4. In the `<head>` section of `exercise1.html`, add a link to the external stylesheet:
   ```html
   <link rel="stylesheet" href="styles.css">
   ```
5. Save both files and refresh your browser to ensure styles still work

**Benefits of external stylesheets:**
- Can be used across multiple HTML pages
- Easier to maintain and organize
- Browser can cache the CSS file for faster loading
- Separates concerns (HTML for structure, CSS for style)

---

## Part 4: Partially Independent Tasks

Now apply what you've learned with less guidance!

### Task 1: Create a Navigation Menu Style

Style the navigation menu (`.nav-menu`) in the HTML:
- Remove default list styling
- Make text uppercase
- Add hover effects that change background color
- Use appropriate colors and spacing
- Make sure links are easy to click

**Hint:** You'll need to style `ul`, `li`, and `a` elements within `.nav-menu`.

### Task 2: Style the Info Boxes

Create CSS rules for elements with class `info-box`:
- Add a colored border on the left side (choose your color)
- Add a light background color
- Add subtle shadows for depth
- Use proper typography (font-size, line-height)
- Add rounded corners

### Task 3: Create a Button Style

Style elements with class `button`:
- Choose colors that stand out but look professional
- Add padding (but don't add padding to this exercise - that's layout!)
- Make text bold and centered
- Remove underline from text
- Add hover effect that changes color
- Add a subtle shadow
- Make corners slightly rounded

### Task 4: Style Code Snippets

Style the `code` element and elements with class `code-block`:
- Use a monospace font family
- Use a light gray background
- Add subtle border
- Make text a different color than regular text
- For `.code-block`, add rounded corners

### Task 5: Create Emphasis Styles

Create three different emphasis classes with distinct visual styles:
- `.warning` - Should look cautionary (yellows/oranges)
- `.success` - Should look positive (greens)
- `.info` - Should look informative (blues)

For each, use appropriate:
- Background colors
- Text colors
- Border styles
- Icons using `::before` pseudo-element with emoji or symbols

### Task 6: Style the Quote Section

Style elements with class `quote`:
- Make text italic
- Use a special font or larger size
- Add a colored left border
- Use `::before` to add opening quote marks (")
- Use `::after` to add closing quote marks (")
- Make the text color different from body text

### Task 7: Create a Hover Gallery Effect

Style elements with class `gallery-item`:
- Add borders and shadows
- Create a hover effect that:
  - Increases shadow intensity
  - Changes border color
  - Slightly changes opacity
- Make images inside have rounded corners

### Task 8: Advanced List Styling

Style the list with class `feature-list`:
- Remove default bullets
- Use `::before` to add custom symbols or emojis as bullets
- Style first item differently from others
- Add subtle background color to alternate items
- Make the last item stand out

---

## Summary

In this exercise, you learned:

✓ What CSS is and why it's important  
✓ CSS syntax (selectors, properties, values)  
✓ Three ways to add CSS (internal, external, inline)  
✓ **Colors**: color, background-color, opacity  
✓ **Typography**: font-family, font-size, font-weight, font-style, line-height, letter-spacing  
✓ **Text formatting**: text-align, text-decoration, text-transform  
✓ **Links**: styling different link states (:link, :visited, :hover, :active)  
✓ **Borders**: border properties and border-radius  
✓ **Shadows**: box-shadow and text-shadow  
✓ **Lists**: list-style-type and list customization  
✓ **Selectors**: class, ID, descendant, child selectors  
✓ **Pseudo-classes**: :first-child, :last-child, :nth-child, :hover, :focus  
✓ **Pseudo-elements**: ::before, ::after, ::first-letter, ::first-line  

These styling techniques will make your websites visually appealing. In Exercise 2, you'll learn about layout properties (box model, positioning, flexbox) to control where elements appear on the page!

## Tips for Success

- **Test frequently**: Open your HTML file in a browser and refresh after each change
- **Use browser DevTools**: Right-click on elements and select "Inspect" to see applied styles
- **Start simple**: Get basic styles working before adding complex effects
- **Use comments**: Add comments in CSS with `/* comment */` to organize your code
- **Be consistent**: Use similar colors, fonts, and spacing throughout
- **Validate your CSS**: Use the W3C CSS Validator to check for errors
- **Experiment**: Try different values to see how they affect the appearance

## Resources

- [MDN CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
- [CSS Color Picker](https://www.google.com/search?q=color+picker)
- [Google Fonts](https://fonts.google.com/) - Free fonts for web use
- [CSS-Tricks](https://css-tricks.com/) - Tutorials and guides

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
   - Type a commit message in the text box at the top (e.g., "Completed Exercise 1 - CSS Basic Selectors")
   - Click the checkmark button (✓) above the message box or press `Ctrl+Enter` (Windows/Linux) or `Cmd+Enter` (Mac)

5. **Push to GitHub**
   - Click the "Sync Changes" button that appears, or
   - Click the three dots menu (•••) and select "Push"

### Using Command Line (Alternative)

If you prefer using the terminal:

```bash
git add exercise1.html styles.css
git commit -m "Completed Exercise 1 - CSS Basic Selectors"
git push
```

Your work is now saved and backed up on GitHub! You can continue to the next exercise.
