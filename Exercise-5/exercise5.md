# Exercise 5 - Responsive Layouts

## Introduction

In this exercise, you will learn about **responsive web design** - the practice of creating websites that adapt and look good on all devices, from mobile phones to desktop computers. Responsive design is essential in modern web development as users access websites from various screen sizes.

**Responsive design** means that your website automatically adjusts its layout, images, and content based on the device's screen size. This provides an optimal viewing experience across all devices.

## Key Concepts

### 1. The Viewport Meta Tag

The viewport meta tag tells browsers how to control the page's dimensions and scaling on different devices.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

**Explanation:**
- `width=device-width` - Sets the width of the page to follow the screen width of the device
- `initial-scale=1.0` - Sets the initial zoom level when the page is first loaded

**Why it's important:** Without this tag, mobile browsers render pages at desktop widths and then scale them down, making content hard to read.

### 2. Media Queries

**Media queries** are CSS techniques that apply different styles based on device characteristics, primarily screen width.

**Syntax:**
```css
@media (max-width: 768px) {
    /* CSS rules that apply when screen width is 768px or less */
    .element {
        font-size: 14px;
    }
}
```

**Common breakpoints:**
- **Mobile devices:** max-width: 480px
- **Tablets:** max-width: 768px
- **Laptops/Desktops:** max-width: 1024px
- **Large screens:** min-width: 1025px

**Explanation of query types:**
- `max-width: 768px` - Applies when screen is 768px or **smaller** (mobile-first approach)
- `min-width: 769px` - Applies when screen is 769px or **larger** (desktop-first approach)

### 3. Flexible Layouts with Flexbox

**Flexbox** (Flexible Box Layout) is a CSS layout model that makes it easy to create responsive layouts that adapt to different screen sizes.

**Basic Flexbox Container:**
```css
.container {
    display: flex;           /* Enables flexbox */
    flex-wrap: wrap;         /* Allows items to wrap to next line */
    gap: 20px;              /* Space between flex items */
}
```

**Flexbox Properties for Containers:**
- `display: flex` - Enables flexbox layout
- `flex-direction: row` - Items arranged horizontally (default)
- `flex-direction: column` - Items arranged vertically
- `flex-wrap: wrap` - Items wrap to multiple lines when needed
- `justify-content` - Aligns items horizontally (main axis)
- `align-items` - Aligns items vertically (cross axis)
- `gap` - Space between items

**Flexbox Properties for Items:**
- `flex: 1` - Item grows to fill available space equally
- `flex-basis: 50%` - Sets the initial size of the item
- `flex-grow: 1` - Allows item to grow if space is available
- `flex-shrink: 1` - Allows item to shrink if needed

### 4. Relative Units

Using relative units instead of fixed pixels makes layouts more flexible:

- `%` - Percentage of parent element
- `em` - Relative to font-size of element
- `rem` - Relative to font-size of root element
- `vw` - 1% of viewport width
- `vh` - 1% of viewport height

---

## Part 1: Guided Steps - Building a Responsive Layout

Follow these steps carefully to create your first responsive website.

### Step 1: Create the HTML Structure

**Your task:**
1. Open `exercise5.html` in your code editor
2. Inside the `<body>` element, add the following structure:

```html
<header class="site-header">
    <h1>My Responsive Website</h1>
    <nav class="main-nav">
        <a href="#home">Home</a>
        <a href="#about">About</a>
        <a href="#services">Services</a>
        <a href="#contact">Contact</a>
    </nav>
</header>

<main class="container">
    <section class="hero">
        <h2>Welcome to Responsive Design</h2>
        <p>This website adapts to different screen sizes!</p>
    </section>
</main>
```

**Explanation:**
- We create a semantic structure with `<header>`, `<nav>`, `<main>`, and `<section>`
- Classes are added for styling purposes

### Step 2: Basic Styling

Add the following CSS inside the `<style>` tag in your HTML file:

```css
/* Reset default margins and paddings */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    color: #333;
}
```

**Explanation:**
- `* { box-sizing: border-box; }` - Makes width/height calculations include padding and border
- Resetting margins/paddings provides a clean slate
- We set base typography for the entire page

### Step 3: Style the Header (Desktop First)

Add this CSS:

```css
.site-header {
    background-color: #2c3e50;
    color: white;
    padding: 1rem 2rem;
}

.site-header h1 {
    font-size: 2rem;
    margin-bottom: 1rem;
}

.main-nav {
    display: flex;
    gap: 2rem;
}

.main-nav a {
    color: white;
    text-decoration: none;
    padding: 0.5rem 1rem;
    border-radius: 4px;
    transition: background-color 0.3s;
}

.main-nav a:hover {
    background-color: #34495e;
}
```

**Explanation:**
- We use `rem` units for flexible sizing
- `display: flex` makes navigation items align horizontally
- `gap: 2rem` adds space between navigation links
- `transition` creates smooth hover effects

### Step 4: Add Media Query for Mobile Navigation

Now we make the navigation responsive. Add this media query:

```css
/* Mobile styles - applies to screens 768px and smaller */
@media (max-width: 768px) {
    .main-nav {
        flex-direction: column;
        gap: 0.5rem;
    }
    
    .site-header h1 {
        font-size: 1.5rem;
    }
}
```

**Explanation:**
- `@media (max-width: 768px)` targets screens 768px or smaller (tablets and phones)
- `flex-direction: column` stacks navigation links vertically on mobile
- We reduce the heading size for smaller screens

**Test your work:** Open the HTML file in a browser and resize the window. The navigation should stack vertically on narrow screens!

### Step 5: Create a Flexible Grid Layout

Add this HTML to your `<main>` element (after the hero section):

```html
<section class="cards-section">
    <h2>Our Services</h2>
    <div class="card-grid">
        <div class="card">
            <h3>Web Design</h3>
            <p>Beautiful, modern website designs that engage your audience.</p>
        </div>
        <div class="card">
            <h3>Development</h3>
            <p>Clean, efficient code that brings designs to life.</p>
        </div>
        <div class="card">
            <h3>SEO</h3>
            <p>Optimize your site to rank higher in search results.</p>
        </div>
    </div>
</section>
```

Now add this CSS:

```css
.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
}

.hero {
    text-align: center;
    padding: 3rem 1rem;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    border-radius: 8px;
    margin-bottom: 2rem;
}

.hero h2 {
    font-size: 2.5rem;
    margin-bottom: 1rem;
}

.cards-section h2 {
    text-align: center;
    margin-bottom: 2rem;
    font-size: 2rem;
}

.card-grid {
    display: flex;
    gap: 2rem;
    flex-wrap: wrap;
}

.card {
    flex: 1 1 300px;
    background-color: #f8f9fa;
    padding: 2rem;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    transition: transform 0.3s, box-shadow 0.3s;
}

.card:hover {
    transform: translateY(-5px);
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
}

.card h3 {
    color: #2c3e50;
    margin-bottom: 1rem;
}
```

**Explanation:**
- `max-width: 1200px` - Container doesn't get too wide on large screens
- `margin: 0 auto` - Centers the container
- `display: flex` with `flex-wrap: wrap` - Creates a flexible grid
- `flex: 1 1 300px` - Cards grow and shrink, but maintain minimum 300px width
- When space is limited, cards wrap to the next line automatically!

### Step 6: Make Cards Responsive

Add this media query:

```css
/* Tablet styles */
@media (max-width: 768px) {
    .card {
        flex: 1 1 calc(50% - 1rem);
    }
    
    .hero h2 {
        font-size: 2rem;
    }
}

/* Mobile styles */
@media (max-width: 480px) {
    .container {
        padding: 1rem;
    }
    
    .card {
        flex: 1 1 100%;
    }
    
    .hero {
        padding: 2rem 1rem;
    }
    
    .hero h2 {
        font-size: 1.5rem;
    }
    
    .card-grid {
        gap: 1rem;
    }
}
```

**Explanation:**
- **Tablet (768px):** Cards display 2 per row
- **Mobile (480px):** Cards stack in a single column (100% width)
- We progressively reduce font sizes and spacing for smaller screens

**Test your work:** Resize your browser window to see the cards rearrange!

### Step 7: Add a Responsive Image

Add this HTML inside the hero section (before the paragraph):

```html
<img src="https://via.placeholder.com/800x400/667eea/ffffff?text=Responsive+Design" alt="Responsive Design Illustration" class="hero-image">
```

Add this CSS:

```css
.hero-image {
    max-width: 100%;
    height: auto;
    border-radius: 8px;
    margin-bottom: 1rem;
}
```

**Explanation:**
- `max-width: 100%` - Image never exceeds container width
- `height: auto` - Maintains aspect ratio
- This makes images responsive by default!

---

## Part 2: Partially Independent Tasks

Now apply what you've learned with less guidance.

### Task 1: Create a Responsive Two-Column Layout

Create a new section in your HTML with:
- A main content area (should be 70% width on desktop)
- A sidebar (should be 30% width on desktop)
- On mobile (max-width: 768px), both should stack vertically at 100% width
- Add some dummy content to both areas

**Hints:**
- Use flexbox with `flex-basis` to set widths
- Use a media query to change layout on mobile
- Don't forget `flex-wrap: wrap`

### Task 2: Make the Navigation Mobile-Friendly

Enhance your navigation:
- Add a `.nav-toggle` button that only appears on mobile (display: none on desktop)
- Style the button to look like a hamburger menu icon (you can use text: "☰")
- Position it in the top-right corner on mobile

**Hints:**
- Use `@media` to show/hide elements
- Use `position: absolute` or flexbox for positioning
- Add appropriate padding and styling

### Task 3: Create a Responsive Footer

Add a footer to your page with:
- Three columns of content (company info, quick links, social media)
- On desktop: 3 columns side by side
- On tablet (max-width: 768px): 2 columns, then 1 column below
- On mobile (max-width: 480px): All stack vertically

**Hints:**
- Use flexbox with `flex-wrap: wrap`
- Use `flex-basis` with percentages
- Adjust `flex-basis` in media queries

### Task 4: Add a Responsive Typography Scale

Create different heading and paragraph sizes for different screen sizes:
- Desktop: h1 (3rem), h2 (2.5rem), h3 (2rem), p (1rem)
- Tablet: h1 (2.5rem), h2 (2rem), h3 (1.5rem), p (1rem)
- Mobile: h1 (2rem), h2 (1.5rem), h3 (1.25rem), p (0.95rem)

**Hints:**
- Define base sizes, then override in media queries
- Use `rem` units for scalability

### Task 5: Create Responsive Padding and Margins

Review your layout and create a consistent spacing system:
- Desktop: Use 2rem for section padding, 1.5rem for margins
- Tablet: Use 1.5rem for section padding, 1rem for margins
- Mobile: Use 1rem for section padding, 0.5rem for margins

**Hints:**
- Create utility classes or adjust existing elements
- Think about improving readability and touch targets on mobile

---

## Part 3: Challenge Exercise

### Challenge: Build a Complete Responsive Portfolio Page

Create a complete responsive portfolio website from scratch with the following requirements:

#### Requirements:

1. **Responsive Navigation Bar**
   - Logo on the left, navigation links on the right
   - Hamburger menu on mobile
   - Sticky/fixed position (stays at top when scrolling)

2. **Hero Section**
   - Full viewport height (use `height: 100vh`)
   - Centered content
   - Responsive background image or gradient
   - Call-to-action button

3. **About Section**
   - Two-column layout (image and text)
   - Columns stack on mobile
   - Responsive image

4. **Projects Gallery**
   - Grid of project cards (3 columns on desktop)
   - 2 columns on tablet
   - 1 column on mobile
   - Hover effects

5. **Contact Form Section**
   - Form with name, email, message fields
   - Form fields should be full width on mobile
   - Submit button

6. **Responsive Footer**
   - Copyright information
   - Social media links
   - Multiple columns that stack on mobile

#### Technical Requirements:
- Use at least 3 different breakpoints
- Use flexbox for layouts
- All images must be responsive
- Include smooth transitions and hover effects
- Use relative units (rem, %, vw/vh)
- Test on mobile (< 480px), tablet (481px - 768px), and desktop (> 768px)

#### Bonus Features:
- Add smooth scrolling to anchor links
- Implement a "scroll to top" button
- Add CSS animations (e.g., fade-in effects)
- Create a dark theme using CSS variables and media query for `prefers-color-scheme`

---

## Testing Your Responsive Design

### How to Test:

1. **Browser DevTools:**
   - Press F12 in Chrome/Firefox
   - Click the device toolbar icon (or Ctrl+Shift+M)
   - Test different device sizes

2. **Browser Resize:**
   - Manually resize your browser window
   - Watch how elements reflow

3. **Real Devices:**
   - Test on actual phones and tablets if available

### Common Screen Sizes to Test:

- **Mobile:** 320px, 375px, 414px (portrait)
- **Tablet:** 768px, 1024px (portrait and landscape)
- **Desktop:** 1280px, 1440px, 1920px

---

## Summary

In this exercise, you learned:

✓ What responsive web design is and why it's important  
✓ How to use the viewport meta tag  
✓ How to create and use media queries  
✓ How to build flexible layouts with Flexbox  
✓ How to make images responsive  
✓ How to use relative units for flexibility  
✓ How to test responsive designs  
✓ Progressive enhancement from mobile to desktop  
✓ Common breakpoints for different devices  
✓ Best practices for responsive typography and spacing  

These skills are essential for modern web development. Every professional website today must be responsive!

## Best Practices

### Mobile-First Approach
- Design for mobile first, then add styles for larger screens
- Use `min-width` media queries to progressively enhance

### Performance
- Use responsive images (different sizes for different screens)
- Minimize CSS for unused breakpoints
- Consider using CSS Grid for complex layouts

### Accessibility
- Ensure touch targets are at least 44x44 pixels on mobile
- Maintain readable font sizes (minimum 16px for body text)
- Don't hide important content on mobile

### Common Pitfalls to Avoid
- ❌ Fixed pixel widths for containers
- ❌ Forgetting the viewport meta tag
- ❌ Not testing on real devices
- ❌ Ignoring landscape orientation on mobile
- ❌ Making text too small on mobile

### Tips
- Start with mobile styles (mobile-first)
- Use flexbox for simple layouts, CSS Grid for complex ones
- Keep breakpoints simple (3-4 is usually enough)
- Test frequently as you build
- Use browser DevTools device emulation
- Think in proportions, not pixels

## Additional Resources

- [MDN Media Queries Guide](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries)
- [CSS Tricks - A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Responsive Design Principles](https://web.dev/responsive-web-design-basics/)

---

**Congratulations!** You've completed Exercise 5 on Responsive Layouts. You now have the skills to create websites that work beautifully on any device!

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
   - Type a commit message in the text box at the top (e.g., "Completed Exercise 5 - Responsive Layouts")
   - Click the checkmark button (✓) above the message box or press `Ctrl+Enter` (Windows/Linux) or `Cmd+Enter` (Mac)

5. **Push to GitHub**
   - Click the "Sync Changes" button that appears, or
   - Click the three dots menu (•••) and select "Push"

### Using Command Line (Alternative)

If you prefer using the terminal:

```bash
git add .
git commit -m "Completed Exercise 5 - Responsive Layouts"
git push
```

Your work is now saved and backed up on GitHub! You can continue to the final challenge.
