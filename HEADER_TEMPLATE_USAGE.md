# Header Template Usage Guide

## Overview
The header template system allows you to maintain a single header across all pages without duplicating HTML code. The header is loaded dynamically using JavaScript.

## Files Created
- `header-main.html` - Header template for main pages (index.html)
- `header-suburb.html` - Header template for suburb pages (suburbs/*.html)
- `header-usage-example.html` - Example of how to implement the header system

## How to Use

### 1. For Main Pages (index.html)
```html
<body class="preload">
  <a class="skip-link" href="#main">Skip to content</a>
  
  <!-- Header will be loaded here -->
  <div id="header-placeholder"></div>
  
  <main id="main">
    <!-- Your content -->
  </main>
  
  <!-- Include script.js at bottom -->
  <script defer src="script.js"></script>
</body>
```

### 2. For Suburb Pages (suburbs/*.html)
```html
<body class="preload" data-page="suburb">
  <a class="skip-link" href="#main">Skip to content</a>
  
  <!-- Header will be loaded here -->
  <div id="header-placeholder"></div>
  
  <main id="main">
    <!-- Your content -->  
  </main>
  
  <!-- Include script.js at bottom -->
  <script defer src="../script.js"></script>
</body>
```

### Key Requirements:
1. Add `<div id="header-placeholder"></div>` where you want the header
2. For suburb pages, add `data-page="suburb"` attribute to the body tag
3. Include `script.js` which will automatically load the correct header template
4. Remove the old `<header>` HTML from your pages

### Benefits:
- ✅ Single source of truth for header HTML
- ✅ Easy to maintain and update navigation
- ✅ Consistent styling across all pages  
- ✅ Automatic detection of page type (main vs suburb)
- ✅ All navigation functionality preserved (mobile nav, dropdowns, etc.)

### Next Steps:
1. Update all existing pages to use this template system
2. Remove duplicate header HTML from each page
3. Test navigation functionality on all pages