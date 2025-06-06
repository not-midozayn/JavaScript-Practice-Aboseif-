# HTML Elements Cheat Sheet

## Global Attributes
**Every HTML element can use these attributes:**
- `id` - Unique identifier for the element
- `class` - CSS class names (space-separated)
- `style` - Inline CSS styling
- `title` - Tooltip text shown on hover
- `lang` - Language of the element's content
- `dir` - Text direction ("ltr" or "rtl")
- `hidden` - Hides the element from display
- `tabindex` - Tab order for keyboard navigation
- `contenteditable` - Makes element editable ("true" or "false")
- `draggable` - Makes element draggable ("true" or "false")
- `data-*` - Custom data attributes (e.g., `data-id="123"`)
- Event handlers: `onclick`, `onmouseover`, `onkeydown`, etc.

## Document Structure

### `<html>`
Root element of an HTML document. Contains all other elements.
```html
<html lang="en" dir="ltr">
```
**Attributes:**
- `lang` - Language of the document (e.g., "en", "es", "fr")
- `dir` - Text direction ("ltr" for left-to-right, "rtl" for right-to-left)

### `<head>`
Contains metadata about the document (not displayed on page).
```html
<head>
  <title>Page Title</title>
  <meta charset="UTF-8">
</head>
```
**Attributes:** None (uses global attributes only)

### `<body>`
Contains all visible content of the webpage.
```html
<body onload="init()">
  <!-- Page content goes here -->
</body>
```
**Attributes:**
- `onload` - JavaScript to run when page loads
- `onunload` - JavaScript to run when page unloads

### `<title>`
Sets the page title shown in browser tab and search results.
```html
<title>My Website - Home Page</title>
```
**Attributes:** None (uses global attributes only)

### `<meta>`
Provides metadata about the document.
```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="Page description">
<meta name="keywords" content="html, css, javascript">
<meta name="author" content="John Doe">
<meta http-equiv="refresh" content="30">
```
**Attributes:**
- `charset` - Character encoding (usually "UTF-8")
- `name` - Type of metadata ("viewport", "description", "keywords", "author")
- `content` - Value of the metadata
- `http-equiv` - HTTP header equivalent ("refresh", "content-type")

### `<link>`
Links external resources (CSS, fonts, icons).
```html
<link rel="stylesheet" href="styles.css" type="text/css">
<link rel="icon" href="favicon.ico" type="image/x-icon">
<link rel="preload" href="font.woff2" as="font" type="font/woff2" crossorigin>
```
**Attributes:**
- `rel` - Relationship type ("stylesheet", "icon", "preload", "prefetch")
- `href` - URL of the linked resource
- `type` - MIME type of the resource
- `media` - Media query for conditional loading
- `as` - Type of content being preloaded
- `crossorigin` - CORS settings ("anonymous", "use-credentials")
- `integrity` - Subresource integrity hash

### `<script>`
Embeds or references JavaScript code.
```html
<script src="script.js" defer></script>
<script type="module" src="module.js"></script>
<script>console.log('Hello');</script>
```
**Attributes:**
- `src` - URL of external JavaScript file
- `type` - Script type ("text/javascript", "module")
- `async` - Load script asynchronously
- `defer` - Defer script execution until DOM is parsed
- `crossorigin` - CORS settings
- `integrity` - Subresource integrity hash
- `nomodule` - Fallback for browsers that don't support modules

## Text Content

### `<h1>` to `<h6>`
Headings in order of importance (h1 is most important).
```html
<h1 id="main-title">Main Title</h1>
<h2 class="section-header">Section Title</h2>
<h3>Subsection Title</h3>
```
**Attributes:** Global attributes only
**Use h1 for main page title, h2-h6 for hierarchical structure. Don't skip levels.**

### `<p>`
Paragraph of text.
```html
<p class="intro">This is a paragraph of text.</p>
```
**Attributes:** Global attributes only

### `<span>`
Inline container for styling or scripting purposes.
```html
<span class="highlight" data-tooltip="Important">Important text</span>
```
**Attributes:** Global attributes only

### `<div>`
Block-level container for grouping elements.
```html
<div class="container" role="main">
  <p>Content goes here</p>
</div>
```
**Attributes:**
- `role` - ARIA role for accessibility
- Global attributes

**`<div>` vs `<span>`**: Use div for block-level grouping, span for inline styling. Div creates line breaks, span doesn't.

### `<strong>` vs `<b>`
Both make text bold, but strong has semantic meaning (important).
```html
<strong>Important text</strong> <!-- Preferred for meaningful emphasis -->
<b class="brand-name">Bold text</b> <!-- Pure visual styling -->
```
**Attributes:** Global attributes only
**Use `<strong>` for importance, `<b>` for visual styling only.**

### `<em>` vs `<i>`
Both make text italic, but em has semantic meaning (emphasis).
```html
<em>Emphasized text</em> <!-- Preferred for meaningful emphasis -->
<i class="icon" aria-hidden="true">Italic text</i> <!-- Visual styling or technical terms -->
```
**Attributes:** Global attributes only
**Use `<em>` for emphasis, `<i>` for visual styling or technical terms.**

### `<small>`
Smaller text, often for fine print or legal text.
```html
<small>© 2024 Company Name. All rights reserved.</small>
```
**Attributes:** Global attributes only

### `<mark>`
Highlighted text (like a highlighter marker).
```html
<mark>Highlighted text</mark>
```
**Attributes:** Global attributes only

### `<del>` and `<ins>`
Deleted and inserted text (track changes).
```html
<del cite="https://example.com/change-log" datetime="2024-01-15">Old text</del>
<ins cite="https://example.com/change-log" datetime="2024-01-15">New text</ins>
```
**Attributes:**
- `cite` - URL explaining the change
- `datetime` - Date/time of the change

### `<code>`
Inline code snippets.
```html
<code class="language-js">console.log('Hello')</code>
```
**Attributes:** Global attributes only

### `<pre>`
Preformatted text (preserves whitespace and line breaks).
```html
<pre><code class="language-javascript">
function hello() {
    console.log('Hello World');
}
</code></pre>
```
**Attributes:** Global attributes only

### `<blockquote>`
Block quotations from another source.
```html
<blockquote cite="https://example.com/source">
  <p>This is a quoted text.</p>
  <footer>— <cite>Author Name</cite></footer>
</blockquote>
```
**Attributes:**
- `cite` - URL of the source

## Lists

### `<ul>` and `<li>`
Unordered (bulleted) lists.
```html
<ul class="menu" role="menu">
  <li role="menuitem">First item</li>
  <li role="menuitem">Second item</li>
</ul>
```
**UL Attributes:**
- `role` - ARIA role ("menu", "list")

**LI Attributes:**
- `value` - Value for ordered list items
- `role` - ARIA role ("menuitem", "listitem")

### `<ol>` and `<li>`
Ordered (numbered) lists.
```html
<ol start="5" reversed type="A">
  <li value="7">First step</li>
  <li>Second step</li>
</ol>
```
**OL Attributes:**
- `start` - Starting number
- `reversed` - Reverse the numbering
- `type` - Numbering type ("1", "A", "a", "I", "i")

### `<dl>`, `<dt>`, `<dd>`
Description lists (term and definition pairs).
```html
<dl>
  <dt id="html-term">HTML</dt>
  <dd aria-labelledby="html-term">HyperText Markup Language</dd>
</dl>
```
**Attributes:** Global attributes only

**`<ul>` vs `<ol>`**: Use ul for items where order doesn't matter, ol for sequential steps or rankings.

## Links and Navigation

### `<a>`
Hyperlinks to other pages, sections, or resources.
```html
<a href="https://example.com" target="_blank" rel="noopener">External link</a>
<a href="#section" aria-describedby="section-desc">Internal link</a>
<a href="mailto:email@example.com">Email link</a>
<a href="tel:+1234567890">Phone link</a>
<a download="filename.pdf" href="document.pdf">Download</a>
```
**Attributes:**
- `href` - URL or fragment identifier
- `target` - Where to open link ("_blank", "_self", "_parent", "_top")
- `rel` - Relationship ("noopener", "nofollow", "external")
- `download` - Filename for downloaded files
- `hreflang` - Language of linked document
- `type` - MIME type of linked resource
- `ping` - URLs to ping when link is followed

### `<nav>`
Navigation section containing links.
```html
<nav aria-label="Main navigation" role="navigation">
  <ul>
    <li><a href="/" aria-current="page">Home</a></li>
    <li><a href="/about">About</a></li>
  </ul>
</nav>
```
**Attributes:**
- `aria-label` - Accessible name for the navigation
- `role` - ARIA role (usually "navigation")

## Images and Media

### `<img>`
Embeds images.
```html
<img src="image.jpg" alt="Description of image" width="300" height="200" 
     loading="lazy" decoding="async" fetchpriority="high">
```
**Attributes:**
- `src` - Image URL (required)
- `alt` - Alternative text description (required for accessibility)
- `width` - Image width in pixels
- `height` - Image height in pixels
- `loading` - Loading behavior ("lazy", "eager")
- `decoding` - Decoding hint ("sync", "async", "auto")
- `fetchpriority` - Fetch priority ("high", "low", "auto")
- `crossorigin` - CORS settings
- `usemap` - Image map reference
- `ismap` - Server-side image map
- `sizes` - Image sizes for responsive images
- `srcset` - Multiple image sources

### `<picture>`
Responsive images with multiple sources.
```html
<picture>
  <source media="(min-width: 800px)" srcset="large.jpg" type="image/jpeg">
  <source media="(min-width: 400px)" srcset="medium.webp" type="image/webp">
  <img src="small.jpg" alt="Description" loading="lazy">
</picture>
```
**Picture Attributes:** Global attributes only
**Source Attributes:**
- `srcset` - Image sources with descriptors
- `media` - Media query
- `type` - MIME type
- `sizes` - Image sizes

### `<video>`
Embeds video content.
```html
<video controls width="600" height="400" poster="thumbnail.jpg" preload="metadata">
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.webm" type="video/webm">
  <track kind="subtitles" src="subtitles.vtt" srclang="en" label="English">
  Your browser doesn't support video.
</video>
```
**Attributes:**
- `controls` - Show video controls
- `autoplay` - Auto-play video (use carefully)
- `loop` - Loop the video
- `muted` - Start muted
- `poster` - Thumbnail image URL
- `preload` - Preloading behavior ("none", "metadata", "auto")
- `width`, `height` - Dimensions
- `playsinline` - Play inline on mobile

### `<audio>`
Embeds audio content.
```html
<audio controls preload="none">
  <source src="audio.mp3" type="audio/mpeg">
  <source src="audio.ogg" type="audio/ogg">
  Your browser doesn't support audio.
</audio>
```
**Attributes:**
- `controls` - Show audio controls
- `autoplay` - Auto-play audio
- `loop` - Loop the audio
- `muted` - Start muted
- `preload` - Preloading behavior ("none", "metadata", "auto")

### `<iframe>`
Embeds another webpage or content.
```html
<iframe src="https://example.com" width="600" height="400" 
        title="Description" loading="lazy" sandbox="allow-scripts">
</iframe>
```
**Attributes:**
- `src` - URL to embed
- `width`, `height` - Dimensions
- `title` - Accessible description (required)
- `loading` - Loading behavior ("lazy", "eager")
- `sandbox` - Security restrictions
- `allow` - Permissions policy
- `referrerpolicy` - Referrer policy

## Tables

### `<table>`, `<tr>`, `<td>`, `<th>`
Creates data tables.
```html
<table>
  <caption>Sales Data for Q1 2024</caption>
  <thead>
    <tr>
      <th scope="col" id="name-header">Name</th>
      <th scope="col" id="age-header">Age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td headers="name-header">John</td>
      <td headers="age-header">25</td>
    </tr>
  </tbody>
</table>
```
**Table Attributes:**
- `summary` - Table summary (deprecated, use caption)

**TH Attributes:**
- `scope` - Header scope ("col", "row", "colgroup", "rowgroup")
- `colspan` - Columns to span
- `rowspan` - Rows to span
- `headers` - Associated header IDs

**TD Attributes:**
- `colspan` - Columns to span
- `rowspan` - Rows to span
- `headers` - Associated header IDs

### `<thead>`, `<tbody>`, `<tfoot>`
Table sections for better structure and styling.
```html
<table>
  <thead><!-- Header rows --></thead>
  <tbody><!-- Data rows --></tbody>
  <tfoot><!-- Footer rows --></tfoot>
</table>
```
**Attributes:** Global attributes only

### `<caption>`
Table caption/title.
```html
<table>
  <caption>Sales Data for Q1 2024</caption>
  <!-- table content -->
</table>
```
**Attributes:** Global attributes only

## Forms

### `<form>`
Container for form elements.
```html
<form action="/submit" method="POST" enctype="multipart/form-data" novalidate>
  <!-- form elements -->
</form>
```
**Attributes:**
- `action` - URL to submit form data
- `method` - HTTP method ("GET", "POST")
- `enctype` - Encoding type ("application/x-www-form-urlencoded", "multipart/form-data", "text/plain")
- `target` - Where to display response
- `novalidate` - Disable browser validation
- `autocomplete` - Enable/disable autocomplete ("on", "off")
- `name` - Form name for JavaScript access

### `<input>`
Various input types for user data.
```html
<input type="text" name="username" placeholder="Enter username" 
       required maxlength="50" autocomplete="username">
<input type="email" name="email" required pattern="[^@]+@[^@]+\.[^@]+">
<input type="password" name="password" minlength="8" autocomplete="current-password">
<input type="number" name="age" min="0" max="120" step="1">
<input type="range" name="volume" min="0" max="100" value="50">
<input type="date" name="birthdate" min="1900-01-01" max="2024-12-31">
<input type="checkbox" name="agree" id="agree" checked>
<input type="radio" name="gender" value="male" id="male">
<input type="file" name="upload" accept="image/*" multiple>
<input type="submit" value="Submit">
<input type="reset" value="Reset">
<input type="hidden" name="csrf_token" value="abc123">
```
**Attributes:**
- `type` - Input type (text, email, password, number, etc.)
- `name` - Form field name
- `value` - Default/current value
- `placeholder` - Hint text
- `required` - Make field mandatory
- `disabled` - Disable the input
- `readonly` - Make read-only
- `autocomplete` - Autocomplete behavior
- `pattern` - Regular expression for validation
- `min`, `max` - Minimum/maximum values
- `step` - Step increment for numbers
- `minlength`, `maxlength` - Length constraints
- `size` - Visual size of input
- `multiple` - Allow multiple selections/files
- `accept` - File types to accept
- `checked` - Default checked state (checkbox/radio)
- `form` - Associate with form by ID
- `formaction` - Override form action
- `formmethod` - Override form method

### `<textarea>`
Multi-line text input.
```html
<textarea name="message" rows="4" cols="50" placeholder="Enter your message"
          maxlength="500" wrap="soft" required></textarea>
```
**Attributes:**
- `name` - Form field name
- `rows` - Number of visible rows
- `cols` - Number of visible columns
- `placeholder` - Hint text
- `maxlength` - Maximum character count
- `minlength` - Minimum character count
- `wrap` - Text wrapping ("soft", "hard")
- `required` - Make field mandatory
- `disabled` - Disable the textarea
- `readonly` - Make read-only
- `autocomplete` - Autocomplete behavior
- `form` - Associate with form by ID

### `<select>` and `<option>`
Dropdown selection.
```html
<select name="country" required multiple size="3">
  <option value="">Choose a country</option>
  <optgroup label="North America">
    <option value="us" selected>United States</option>
    <option value="ca">Canada</option>
  </optgroup>
</select>
```
**Select Attributes:**
- `name` - Form field name
- `multiple` - Allow multiple selections
- `size` - Number of visible options
- `required` - Make selection mandatory
- `disabled` - Disable the select
- `form` - Associate with form by ID

**Option Attributes:**
- `value` - Option value
- `selected` - Default selected state
- `disabled` - Disable the option
- `label` - Alternative text

**Optgroup Attributes:**
- `label` - Group label
- `disabled` - Disable entire group

### `<button>`
Clickable buttons.
```html
<button type="submit" form="myform" disabled>Submit Form</button>
<button type="button" onclick="doSomething()">Click Me</button>
<button type="reset" form="myform">Reset Form</button>
```
**Attributes:**
- `type` - Button type ("submit", "reset", "button")
- `name` - Form field name
- `value` - Value sent with form
- `disabled` - Disable the button
- `form` - Associate with form by ID
- `formaction` - Override form action
- `formmethod` - Override form method
- `formenctype` - Override form encoding
- `formtarget` - Override form target
- `formnovalidate` - Skip validation

**`<button>` vs `<input type="button">`**: Button element is more flexible (can contain HTML), input is simpler but text-only.

### `<label>`
Labels for form elements (improves accessibility).
```html
<label for="username">Username:</label>
<input type="text" id="username" name="username">

<!-- Or wrap the input -->
<label>
  Username:
  <input type="text" name="username">
</label>
```
**Attributes:**
- `for` - ID of associated form element
- `form` - Associate with form by ID

### `<fieldset>` and `<legend>`
Groups related form elements.
```html
<fieldset disabled>
  <legend>Personal Information</legend>
  <input type="text" name="firstname" placeholder="First Name">
  <input type="text" name="lastname" placeholder="Last Name">
</fieldset>
```
**Fieldset Attributes:**
- `disabled` - Disable all contained elements
- `form` - Associate with form by ID
- `name` - Fieldset name

**Legend Attributes:** Global attributes only

## Semantic HTML5 Elements

### `<header>`
Header section of page or article.
```html
<header role="banner">
  <h1>Site Title</h1>
  <nav role="navigation"><!-- navigation --></nav>
</header>
```
**Attributes:**
- `role` - ARIA role ("banner" for main header)

### `<main>`
Main content area (only one per page).
```html
<main role="main" id="main-content">
  <article><!-- primary content --></article>
</main>
```
**Attributes:**
- `role` - ARIA role ("main")

### `<section>`
Thematic grouping of content.
```html
<section aria-labelledby="about-heading">
  <h2 id="about-heading">About Us</h2>
  <p>Company information...</p>
</section>
```
**Attributes:**
- `aria-labelledby` - ID of element that labels this section

### `<article>`
Self-contained, reusable content.
```html
<article role="article" itemscope itemtype="https://schema.org/BlogPosting">
  <h2 itemprop="headline">Blog Post Title</h2>
  <time itemprop="datePublished" datetime="2024-01-15">January 15, 2024</time>
  <p itemprop="articleBody">Post content...</p>
</article>
```
**Attributes:**
- `role` - ARIA role ("article")
- Microdata attributes (`itemscope`, `itemtype`, `itemprop`)

**`<section>` vs `<article>`**: Use article for standalone content (blog posts, news articles), section for thematic groupings within a page.

### `<aside>`
Sidebar or tangentially related content.
```html
<aside role="complementary" aria-label="Related content">
  <h3>Related Links</h3>
  <ul><!-- links --></ul>
</aside>
```
**Attributes:**
- `role` - ARIA role ("complementary")
- `aria-label` - Accessible label

### `<footer>`
Footer section of page or article.
```html
<footer role="contentinfo">
  <p>&copy; 2024 Company Name</p>
</footer>
```
**Attributes:**
- `role` - ARIA role ("contentinfo" for main footer)

### `<figure>` and `<figcaption>`
Images, diagrams, code snippets with captions.
```html
<figure role="img" aria-labelledby="chart-caption">
  <img src="chart.png" alt="Sales chart">
  <figcaption id="chart-caption">Q1 2024 Sales Performance</figcaption>
</figure>
```
**Attributes:**
- `role` - ARIA role ("img")
- `aria-labelledby` - ID of caption element

### `<time>`
Represents dates and times.
```html
<time datetime="2024-01-15T10:30:00Z" title="January 15, 2024 at 10:30 AM UTC">
  January 15, 2024
</time>
```
**Attributes:**
- `datetime` - Machine-readable date/time in ISO format

### `<address>`
Contact information for author or document.
```html
<address>
  <p>Contact: <a href="mailto:info@example.com">info@example.com</a></p>
  <p>Phone: <a href="tel:+1234567890">+1 (234) 567-8900</a></p>
</address>
```
**Attributes:** Global attributes only

## Interactive Elements

### `<details>` and `<summary>`
Collapsible content sections.
```html
<details open>
  <summary>Click to expand</summary>
  <p>Hidden content that can be toggled.</p>
</details>
```
**Details Attributes:**
- `open` - Initially expanded state

**Summary Attributes:** Global attributes only

### `<dialog>`
Modal dialogs and popups.
```html
<dialog id="myDialog" open aria-labelledby="dialog-title" role="dialog">
  <h2 id="dialog-title">Dialog Title</h2>
  <p>This is a dialog box.</p>
  <button onclick="closeDialog()">Close</button>
</dialog>
```
**Attributes:**
- `open` - Show the dialog
- `aria-labelledby` - ID of title element
- `role` - ARIA role ("dialog", "alertdialog")

## Less Common but Useful Elements

### `<abbr>`
Abbreviations with full text on hover.
```html
<abbr title="HyperText Markup Language">HTML</abbr>
```
**Attributes:**
- `title` - Full expansion of abbreviation

### `<cite>`
References to creative works.
```html
<cite>The Great Gatsby</cite>
```
**Attributes:** Global attributes only

### `<q>`
Short inline quotations.
```html
<q cite="https://example.com/source">To be or not to be</q>
```
**Attributes:**
- `cite` - URL of the source

### `<kbd>`
Keyboard input.
```html
<kbd>Ctrl</kbd> + <kbd>C</kbd>
```
**Attributes:** Global attributes only

### `<samp>`
Sample output from programs.
```html
<samp class="output">File not found</samp>
```
**Attributes:** Global attributes only

### `<var>`
Variables in mathematical expressions or programming.
```html
<var>x</var> = 5
```
**Attributes:** Global attributes only

### `<sub>` and `<sup>`
Subscript and superscript text.
```html
H<sub>2</sub>O (water)
E = mc<sup>2</sup>
```
**Attributes:** Global attributes only

### `<br>`
Line break (use sparingly).
```html
Line one<br>Line two
```
**Attributes:** Global attributes only

### `<hr>`
Thematic break (horizontal rule).
```html
<hr role="separator">
```
**Attributes:**
- `role` - ARIA role ("separator")

### `<wbr>`
Word break opportunity for long words.
```html
<p>supercali<wbr>fragilistic<wbr>expialidocious</p>
```
**Attributes:** Global attributes only

## Modern Web Components

### `<template>`
Holds client-side content templates.
```html
<template id="my-template">
  <div class="card">
    <h3></h3>
    <p></p>
  </div>
</template>
```
**Attributes:** Global attributes only

### `<slot>`
Placeholder for web component content.
```html
<slot name="header"></slot>
<slot>Default content</slot> <!-- default slot -->
```
**Attributes:**
- `name` - Slot name for targeted content

## Key Principles (Detailed)

### 1. Semantic HTML
**Definition:** Using HTML elements based on their meaning and purpose, not their default appearance.

**Why it matters:**
- Screen readers and assistive technologies understand content structure
- Search engines better index and rank your content
- Code is more maintainable and self-documenting
- CSS and JavaScript can target content more effectively

**Examples:**
```html
<!-- Bad: Using divs for everything -->
<div class="title">Page Title</div>
<div class="paragraph">Some text content</div>
<div class="list">
  <div class="list-item">Item 1</div>
  <div class="list-item">Item 2</div>
</div>

<!-- Good: Using semantic elements -->
<h1>Page Title</h1>
<p>Some text content</p>
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
</ul>
```

**Semantic Structure Example:**
```html
<article>
  <header>
    <h1>Article Title</h1>
    <time datetime="2024-01-15">January 15, 2024</time>
  </header>
  <main>
    <p>Article content...</p>
    <section>
      <h2>Subsection</h2>
      <p>More content...</p>
    </section>
  </main>
  <footer>
    <p>Author: John Doe</p>
  </footer>
</article>
```

### 2. Accessibility (a11y)
**Definition:** Making web content usable by people with disabilities, including visual, auditory, motor, and cognitive impairments.

**Key Practices:**
- **Alt text for images:** Describe the content and function of images
- **Proper heading hierarchy:** Use h1-h6 in logical order
- **Form labels:** Every input should have an associated label
- **Keyboard navigation:** All interactive elements should be keyboard accessible
- **Color contrast:** Ensure sufficient contrast ratios (4.5:1 for normal text)
- **Focus indicators:** Visible focus states for keyboard users
- **ARIA attributes:** Enhance semantics when HTML isn't enough

**Examples:**
```html
<!-- Image accessibility -->
<img src="chart.jpg" alt="Sales increased 25% from Q1 to Q2 2024">

<!-- Form accessibility -->
<label for="email">Email Address (required)</label>
<input type="email" id="email" name="email" required aria-describedby="email-error">
<div id="email-error" role="alert" aria-live="polite"></div>

<!-- Navigation accessibility -->
<nav aria-label="Main navigation">
  <ul>
    <li><a href="/" aria-current="page">Home</a></li>
    <li><a href="/about">About</a></li>
  </ul>
</nav>

<!-- Skip link for keyboard users -->
<a href="#main-content" class="skip-link">Skip to main content</a>
```

### 3. Progressive Enhancement
**Definition:** Building web pages that work on all devices and browsers, starting with basic functionality and enhancing with advanced features.

**Approach:**
1. **HTML first:** Ensure content is accessible without CSS or JavaScript
2. **CSS enhancement:** Add styling and layout improvements
3. **JavaScript enhancement:** Add interactive features
4. **Feature detection:** Check for support before using advanced features

**Examples:**
```html
<!-- Basic form that works without JavaScript -->
<form action="/search" method="GET">
  <label for="search">Search:</label>
  <input type="search" id="search" name="q" required>
  <button type="submit">Search</button>
</form>

<!-- Enhanced with JavaScript for instant results -->
<form action="/search" method="GET" id="search-form">
  <label for="search">Search:</label>
  <input type="search" id="search" name="q" required 
         data-autocomplete="/api/suggestions">
  <button type="submit">Search</button>
  <div id="suggestions" aria-live="polite"></div>
</form>
```

### 4. Performance Optimization
**Definition:** Techniques to make web pages load faster and run more efficiently.

**Key Strategies:**
- **Image optimization:** Use appropriate formats (WebP, AVIF) and lazy loading
- **Resource hints:** Preload, prefetch, and preconnect critical resources
- **Minimize HTTP requests:** Combine files, use sprites, inline critical CSS
- **Compression:** Enable gzip/brotli compression
- **Caching:** Use appropriate cache headers

**Examples:**
```html
<!-- Optimized images -->
<picture>
  <source srcset="hero.avif" type="image/avif">
  <source srcset="hero.webp" type="image/webp">
  <img src="hero.jpg" alt="Hero image" loading="lazy" 
       width="800" height="400" fetchpriority="high">
</picture>

<!-- Resource hints -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preload" href="critical.css" as="style">
<link rel="prefetch" href="next-page.html">

<!-- Lazy loading -->
<img src="image.jpg" alt="Description" loading="lazy">
<iframe src="embed.html" loading="lazy"></iframe>
```

### 5. SEO (Search Engine Optimization)
**Definition:** Optimizing HTML structure and content to improve search engine rankings and visibility.

**Best Practices:**
- **Title tags:** Unique, descriptive titles for each page
- **Meta descriptions:** Compelling summaries for search results
- **Heading hierarchy:** Clear content structure with h1-h6
- **Structured data:** Schema.org markup for rich snippets
- **Open Graph tags:** Social media sharing optimization

**Examples:**
```html
<!-- SEO-optimized head section -->
<head>
  <title>Best Coffee Beans | Premium Roasted Coffee - CoffeeShop</title>
  <meta name="description" content="Discover our premium coffee beans, expertly roasted for the perfect cup. Free shipping on orders over $25.">
  <meta name="keywords" content="coffee beans, premium coffee, roasted coffee">
  
  <!-- Open Graph for social sharing -->
  <meta property="og:title" content="Best Coffee Beans | Premium Roasted Coffee">
  <meta property="og:description" content="Discover our premium coffee beans, expertly roasted for the perfect cup.">
  <meta property="og:image" content="https://example.com/coffee-beans.jpg">
  <meta property="og:url" content="https://example.com/coffee-beans">
  
  <!-- Structured data -->
  <script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "Product",
    "name": "Premium Coffee Beans",
    "description": "Expertly roasted coffee beans",
    "brand": "CoffeeShop"
  }
  </script>
</head>
```

### 6. Validation and Standards Compliance
**Definition:** Ensuring HTML code follows W3C standards and validates correctly.

**Benefits:**
- Cross-browser compatibility
- Better accessibility
- Easier maintenance
- Future-proofing

**Tools:**
- W3C Markup Validator
- HTML5 validators
- Browser developer tools
- Accessibility checkers

## Essential HTML Terms for Modern Web Development

### DOM (Document Object Model)
**Definition:** Programming interface that represents HTML documents as a tree structure of objects.
```html
<!-- This HTML creates DOM nodes -->
<div id="container">
  <p class="text">Hello World</p>
</div>
```
**JavaScript DOM manipulation:**
```javascript
document.getElementById('container').querySelector('.text').textContent = 'Updated!';
```

### Semantic Elements
**Definition:** HTML5 elements that provide meaning to content structure.
**Examples:** `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<aside>`, `<footer>`

### ARIA (Accessible Rich Internet Applications)
**Definition:** Set of attributes that enhance HTML semantics for assistive technologies.
```html
<button aria-expanded="false" aria-controls="dropdown-menu">Menu</button>
<div id="dropdown-menu" role="menu" aria-hidden="true">
  <a href="#" role="menuitem">Home</a>
</div>
```

### Viewport
**Definition:** The visible area of a web page on a device.
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### Progressive Web App (PWA)
**Definition:** Web applications that use modern web capabilities to provide app-like experiences.
```html
<!-- PWA manifest -->
<link rel="manifest" href="/manifest.json">
<meta name="theme-color" content="#000000">

<!-- Service worker registration -->
<script>
if ('serviceWorker' in navigator) {
  navigator.serviceWorker.register('/sw.js');
}
</script>
```

### Web Components
**Definition:** Custom HTML elements that encapsulate functionality.
```html
<!-- Custom element usage -->
<my-custom-button type="primary">Click me</my-custom-button>

<!-- Shadow DOM -->
<div id="host"></div>
<script>
const host = document.getElementById('host');
const shadow = host.attachShadow({mode: 'open'});
shadow.innerHTML = '<p>Shadow DOM content</p>';
</script>
```

### Responsive Design
**Definition:** Design approach that makes web pages render well on various devices and screen sizes.
```html
<!-- Responsive images -->
<img src="small.jpg" 
     srcset="small.jpg 480w, medium.jpg 800w, large.jpg 1200w"
     sizes="(max-width: 480px) 100vw, (max-width: 800px) 50vw, 25vw"
     alt="Responsive image">

<!-- Responsive embed -->
<div class="video-container">
  <iframe src="video.html" title="Video"></iframe>
</div>
```

### Critical Rendering Path
**Definition:** The sequence of steps browsers follow to render a page.
```html
<!-- Optimize critical rendering path -->
<head>
  <!-- Critical CSS inline -->
  <style>
    .hero { background: blue; height: 100vh; }
  </style>
  
  <!-- Non-critical CSS loaded asynchronously -->
  <link rel="preload" href="styles.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
  <noscript><link rel="stylesheet" href="styles.css"></noscript>
</head>
```

### Content Security Policy (CSP)
**Definition:** Security feature that helps prevent XSS attacks by controlling resource loading.
```html
<meta http-equiv="Content-Security-Policy" 
      content="default-src 'self'; script-src 'self' 'unsafe-inline'; style-src 'self' 'unsafe-inline'">
```

### Microdata and Structured Data
**Definition:** HTML attributes that provide structured information about page content.
```html
<article itemscope itemtype="https://schema.org/Recipe">
  <h1 itemprop="name">Chocolate Chip Cookies</h1>
  <img itemprop="image" src="cookies.jpg" alt="Cookies">
  <div itemprop="description">Delicious homemade cookies</div>
  <time itemprop="cookTime" datetime="PT30M">30 minutes</time>
</article>
```

### Web Accessibility Guidelines (WCAG)
**Definition:** International standards for web accessibility with three levels (A, AA, AAA).
```html
<!-- WCAG compliant form -->
<fieldset>
  <legend>Contact Information</legend>
  <div class="form-group">
    <label for="name">Full Name <span aria-label="required">*</span></label>
    <input type="text" id="name" name="name" required 
           aria-describedby="name-error" autocomplete="name">
    <div id="name-error" role="alert" aria-live="assertive"></div>
  </div>
</fieldset>
```

### Single-Page Application (SPA)
**Definition:** Web applications that load a single HTML document and dynamically update content.
```html
<!-- SPA shell -->
<!DOCTYPE html>
<html>
<head>
  <title>SPA App</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
  <div id="app">
    <!-- Content injected by JavaScript -->
  </div>
  <script src="app.js"></script>
</body>
</html>
```

### Server-Side Rendering (SSR)
**Definition:** Rendering web pages on the server before sending to the client.
```html
<!-- SSR-generated HTML with hydration markers -->
<div id="app" data-server-rendered="true">
  <h1>Welcome to Our Site</h1>
  <div class="content">
    <!-- Pre-rendered content -->
  </div>
</div>
<script>
  // Client-side hydration
  window.__INITIAL_STATE__ = { /* server data */ };
</script>
```

### Web Performance Metrics
**Definition:** Measurements used to evaluate website performance.

**Core Web Vitals:**
- **LCP (Largest Contentful Paint):** Loading performance
- **FID (First Input Delay):** Interactivity
- **CLS (Cumulative Layout Shift):** Visual stability

```html
<!-- Optimize for Core Web Vitals -->
<img src="hero.jpg" alt="Hero" width="800" height="400" 
     loading="eager" fetchpriority="high">
<link rel="preload" href="critical.css" as="style">
<link rel="preload" href="main.js" as="script">
```

### HTTP/2 and HTTP/3
**Definition:** Modern HTTP protocols that improve web performance.
```html
<!-- HTTP/2 Server Push hints -->
<link rel="preload" href="style.css" as="style">
<link rel="preload" href="script.js" as="script">
<link rel="preload" href="font.woff2" as="font" type="font/woff2" crossorigin>
```

## Common Combinations

### Card Pattern
```html
<article class="card" itemscope itemtype="https://schema.org/Product">
  <header>
    <img itemprop="image" src="product.jpg" alt="Product image" loading="lazy">
    <h2 itemprop="name">Product Name</h2>
  </header>
  <div class="card-content">
    <p itemprop="description">Product description...</p>
    <div class="price" itemprop="offers" itemscope itemtype="https://schema.org/Offer">
      <span itemprop="price">$99.99</span>
      <meta itemprop="priceCurrency" content="USD">
    </div>
  </div>
  <footer>
    <button type="button" aria-describedby="cart-help">Add to Cart</button>
    <div id="cart-help" role="tooltip" aria-hidden="true">
      Click to add this item to your shopping cart
    </div>
  </footer>
</article>
```

### Navigation Menu
```html
<nav role="navigation" aria-label="Main navigation">
  <ul role="menubar">
    <li role="none">
      <a href="/" role="menuitem" aria-current="page">Home</a>
    </li>
    <li role="none">
      <button role="menuitem" aria-expanded="false" aria-haspopup="true" 
              id="products-menu">Products</button>
      <ul role="menu" aria-labelledby="products-menu" hidden>
        <li role="none">
          <a href="/laptops" role="menuitem">Laptops</a>
        </li>
        <li role="none">
          <a href="/phones" role="menuitem">Phones</a>
        </li>
      </ul>
    </li>
  </ul>
</nav>
```

### Accessible Form with Validation
```html
<form novalidate aria-label="Contact form">
  <fieldset>
    <legend>Contact Information</legend>
    
    <div class="form-group">
      <label for="email">Email Address <span aria-label="required">*</span></label>
      <input type="email" id="email" name="email" required 
             aria-describedby="email-error email-help"
             autocomplete="email" spellcheck="false">
      <div id="email-help" class="help-text">
        We'll never share your email address
      </div>
      <div id="email-error" class="error" role="alert" aria-live="polite"></div>
    </div>
    
    <div class="form-group">
      <label for="message">Message <span aria-label="required">*</span></label>
      <textarea id="message" name="message" required rows="4"
                aria-describedby="message-error message-help"
                maxlength="500"></textarea>
      <div id="message-help" class="help-text">
        Maximum 500 characters
      </div>
      <div id="message-error" class="error" role="alert" aria-live="polite"></div>
    </div>
  </fieldset>
  
  <div class="form-actions">
    <button type="submit">Send Message</button>
    <button type="reset">Clear Form</button>
  </div>
</form>
```

### Modal Dialog
```html
<dialog id="confirmation-dialog" role="dialog" aria-labelledby="dialog-title" 
        aria-describedby="dialog-description">
  <header>
    <h2 id="dialog-title">Confirm Action</h2>
    <button type="button" aria-label="Close dialog" onclick="closeDialog()">
      <span aria-hidden="true">&times;</span>
    </button>
  </header>
  <main>
    <p id="dialog-description">
      Are you sure you want to delete this item? This action cannot be undone.
    </p>
  </main>
  <footer>
    <button type="button" onclick="confirmAction()" autofocus>Delete</button>
    <button type="button" onclick="closeDialog()">Cancel</button>
  </footer>
</dialog>
```

This comprehensive cheat sheet covers the essential HTML elements, their attributes, and modern web development concepts you'll encounter in building contemporary web applications. Remember to always prioritize semantic markup, accessibility, and progressive enhancement in your HTML structure.
      