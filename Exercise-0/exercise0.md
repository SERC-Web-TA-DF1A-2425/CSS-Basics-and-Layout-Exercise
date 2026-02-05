# Exercise 0 - HTML Structure and Basic Elements

## Introduction

In this exercise, you will learn about HTML document structure and practice using basic HTML elements. This is a foundational exercise that will prepare you for more advanced CSS and layout work.

HTML (HyperText Markup Language) is the standard language for creating web pages. It uses **elements** (also called tags) to structure content and define its meaning.

## HTML Document Structure

Every HTML document has a basic structure that looks like this:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Page Title</title>
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
    </head>
    <body>
        <!-- Your content goes here -->
    </body>
</html>
```

**Explanation of the structure:**

- `<!DOCTYPE html>` - Tells the browser this is an HTML5 document
- `<html>` - The root element that contains all other HTML elements
- `<head>` - Contains metadata about the document (not visible on the page)
  - `<meta charset="UTF-8">` - Specifies the character encoding
  - `<title>` - Sets the page title (appears in browser tab)
  - `<meta name="viewport">` - Makes the page responsive on mobile devices
- `<body>` - Contains all the visible content of the page

## Understanding Block vs Inline Elements

HTML elements are categorized into two main types based on how they display:

### Block Elements
- Take up the **full width** available
- Always start on a **new line**
- Can contain other block or inline elements
- Examples: `<div>`, `<p>`, `<h1>-<h6>`, `<ul>`, `<ol>`, `<li>`

### Inline Elements
- Only take up as **much width as necessary**
- Do **not** start on a new line
- Flow within the text
- Examples: `<span>`, `<a>`, `<strong>`, `<em>`, `<img>`

---

## Part 1: Guided Steps - Basic HTML Elements

Follow these steps to practice using basic HTML elements.

### Step 1: Headings

HTML has six levels of headings, from `<h1>` (most important) to `<h6>` (least important).

**Type:** Block elements

**How to use:**
```html
<h1>Main Heading</h1>
<h2>Subheading</h2>
<h3>Smaller Subheading</h3>
```

**Your task:**
1. Open `exercise0.html` in your code editor
2. Inside the `<body>` element, add an `<h1>` heading with the text "Welcome to HTML Basics"
3. Below it, add an `<h2>` heading with the text "Learning HTML Elements"

### Step 2: Paragraphs

The `<p>` element is used to define paragraphs of text.

**Type:** Block element

**How to use:**
```html
<p>This is a paragraph of text. It can contain multiple sentences.</p>
```

**Your task:**
1. Below your headings, add a paragraph with this text: "HTML is the foundation of web development. It provides structure to web pages."
2. Add another paragraph with this text: "In this exercise, we will practice using different HTML elements."

### Step 3: Text Formatting

HTML provides elements to format text inline:

- `<strong>` - Makes text bold and indicates importance (inline)
- `<em>` - Makes text italic and adds emphasis (inline)

**Type:** Inline elements

**How to use:**
```html
<p>This is <strong>very important</strong> text.</p>
<p>This is <em>emphasized</em> text.</p>
```

**Your task:**
1. In your second paragraph, make the word "practice" bold using `<strong>`
2. Make the word "different" italic using `<em>`

### Step 4: Links

The `<a>` (anchor) element creates hyperlinks to other pages or resources.

**Type:** Inline element

**How to use:**
```html
<a href="https://www.example.com">Visit Example</a>
```

**Attributes:**
- `href` - The URL the link points to
- `target="_blank"` - (optional) Opens link in a new tab

**Your task:**
1. Add a paragraph with the text: "Learn more about HTML at "
2. Inside that paragraph, add a link to "https://developer.mozilla.org/en-US/docs/Web/HTML" with the link text "MDN Web Docs"
3. Add the `target="_blank"` attribute to open the link in a new tab

### Step 5: Lists

HTML supports two types of lists:

**Unordered Lists (`<ul>`)** - Bulleted lists

**Type:** `<ul>` and `<li>` are block elements

**How to use:**
```html
<ul>
    <li>First item</li>
    <li>Second item</li>
    <li>Third item</li>
</ul>
```

**Ordered Lists (`<ol>`)** - Numbered lists

**Type:** `<ol>` and `<li>` are block elements

**How to use:**
```html
<ol>
    <li>First item</li>
    <li>Second item</li>
    <li>Third item</li>
</ol>
```

**Your task:**
1. Add an `<h3>` heading with the text "My Favorite Programming Languages"
2. Below it, create an unordered list with three programming languages of your choice
3. Add another `<h3>` heading with the text "Steps to Create a Website"
4. Below it, create an ordered list with these items:
   - Plan your content
   - Write HTML
   - Add CSS styling

### Step 6: Images

The `<img>` element embeds images in your page.

**Type:** Inline element (but behaves uniquely)

**How to use:**
```html
<img src="image.jpg" alt="Description of image">
```

**Attributes:**
- `src` - Path to the image file (required)
- `alt` - Alternative text for accessibility (required)
- `width` and `height` - (optional) Dimensions of the image

**Note:** `<img>` is a **self-closing tag** (it doesn't have a closing tag)

**Your task:**
1. Add an `<h3>` heading with the text "HTML Logo"
2. Below it, add an image using this URL: `https://www.w3.org/html/logo/img/mark-word-icon.png`
3. Set the `alt` attribute to "HTML5 Logo"
4. Set the `width` to "200"

### Step 7: Division (`<div>`) and Span

**The `<div>` element** is a generic container used to group content.

**Type:** Block element

**How to use:**
```html
<div>
    <h2>Section Title</h2>
    <p>Section content goes here.</p>
</div>
```

**The `<span>` element** is a generic inline container used to group inline content.

**Type:** Inline element

**How to use:**
```html
<p>This is <span>inline text</span> in a paragraph.</p>
```

**Your task:**
1. Create a `<div>` that contains:
   - An `<h3>` heading with "About Me"
   - A paragraph with a brief introduction about yourself
2. In that paragraph, use `<span>` to wrap your name

### Step 8: Line Breaks and Horizontal Rules

**Line Break (`<br>`)** - Creates a line break

**Type:** Inline element (self-closing)

**Horizontal Rule (`<hr>`)** - Creates a horizontal line (thematic break)

**Type:** Block element (self-closing)

**How to use:**
```html
<p>First line<br>Second line</p>
<hr>
<p>Content after the line</p>
```

**Your task:**
1. Add a paragraph with your address, using `<br>` to separate each line (street, city, country)
2. Add an `<hr>` element to create a visual separator

---

## Part 2: Partially Independent Tasks

Now that you've practiced the basics, complete these tasks with less guidance:

### Task 1: Create a Recipe Page Section

Create a section that includes:
- An `<h2>` heading with a recipe name of your choice
- A paragraph describing the recipe
- An unordered list of ingredients (at least 4 items)
- An ordered list of preparation steps (at least 3 steps)
- Use `<strong>` to emphasize important cooking terms
- Add an `<hr>` to separate this section from the next

### Task 2: Create a Contact Information Section

Create a section with:
- An `<h2>` heading "Contact Information"
- A `<div>` containing:
  - A paragraph with "Email: " followed by a link to an email (use `mailto:` in href)
  - A paragraph with "Phone: " followed by a phone number
  - Use `<br>` where appropriate
- Another `<div>` containing a list of social media links (at least 3)

### Task 3: Create a Favorites Gallery

Create a section with:
- An `<h2>` heading "My Favorites"
- Three `<div>` elements, each containing:
  - An `<h3>` with a category name (e.g., "Favorite Book", "Favorite Movie", "Favorite Food")
  - A paragraph describing why it's your favorite
  - Use both `<strong>` and `<em>` in at least one paragraph

### Task 4: Block vs Inline Demonstration

Create a section to demonstrate the difference between block and inline elements:
- Add an `<h2>` heading "Block vs Inline Elements"
- Create a paragraph that explains: "Block elements take the full width available, while inline elements only take necessary space."
- Add three `<div>` elements, each with the text "I am a block element" (notice how they stack)
- Add a paragraph containing three `<span>` elements with the text "I am inline" (notice how they flow)

---

## Summary

In this exercise, you learned:

✓ The basic structure of an HTML document  
✓ The difference between block and inline elements  
✓ How to use headings (`<h1>` - `<h6>`)  
✓ How to create paragraphs (`<p>`)  
✓ How to format text with `<strong>` and `<em>`  
✓ How to create links with `<a>`  
✓ How to create lists with `<ul>`, `<ol>`, and `<li>`  
✓ How to embed images with `<img>`  
✓ How to use containers with `<div>` and `<span>`  
✓ How to use `<br>` and `<hr>` for breaks  

These are the fundamental building blocks of HTML. In future exercises, you'll learn how to style these elements with CSS and create more complex layouts!

## Tips

- Always close your tags (except self-closing tags like `<img>`, `<br>`, `<hr>`)
- Use proper indentation to make your code readable
- Use meaningful `alt` text for images (helps with accessibility)
- Test your page in a browser frequently to see your changes
- Remember: Block elements stack vertically, inline elements flow horizontally

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
   - Type a commit message in the text box at the top (e.g., "Completed Exercise 0 - HTML Structure and Basic Elements")
   - Click the checkmark button (✓) above the message box or press `Ctrl+Enter` (Windows/Linux) or `Cmd+Enter` (Mac)

5. **Push to GitHub**
   - Click the "Sync Changes" button that appears, or
   - Click the three dots menu (•••) and select "Push"

### Using Command Line (Alternative)

If you prefer using the terminal:

```bash
git add exercise0.html
git commit -m "Completed Exercise 0 - HTML Structure and Basic Elements"
git push
```

Your work is now saved and backed up on GitHub! You can continue to the next exercise.
