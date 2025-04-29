# Landing Page Maintenance Guide

This guide will help you maintain and customize the Nachtbril Over Bril landing page. Whether you're new to web development or need a quick reference, follow these detailed instructions for common updates.

## Table of Contents
1. [Updating Text and Tailwind CSS Classes](#updating-text-and-tailwind-css-classes)
2. [Fixing Broken Links](#fixing-broken-links)
3. [Adding Privacy and Terms Pages](#adding-privacy-and-terms-pages)
4. [Troubleshooting](#troubleshooting)

## Updating Text and Tailwind CSS Classes

### Header Section
The header contains your logo and navigation menu. To update:

1. **Logo Text:**
```html
<!-- Find this line in the header -->
<a href="/" class="text-2xl font-bold text-blue-600">NachtBril</a>
```
- Replace "NachtBril" with your desired text
- Adjust size using `text-2xl` (options: text-sm, text-base, text-lg, text-2xl, text-3xl)
- Change color using `text-blue-600` (options: text-red-600, text-green-600, etc.)

2. **Navigation Links:**
```html
<div class="hidden md:flex space-x-8">
    <a href="#features" class="text-gray-600 hover:text-blue-600">Kenmerken</a>
    <!-- More links -->
</div>
```
- Replace "Kenmerken" with your desired text
- `hidden md:flex` means hidden on mobile, visible on medium screens
- `space-x-8` controls spacing between links

### Hero Section
```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 mb-6">
    Nachtbril Over Bril
    <span class="block text-blue-600 mt-2">Nu 20% Korting!</span>
</h1>
```
- Update heading sizes using `text-4xl` etc.
- Adjust margins with `mb-6` (margin-bottom) or `mt-2` (margin-top)
- Numbers represent spacing units (4=1rem, 6=1.5rem)

### Features Section
```html
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
```
- `grid-cols-1`: One column on mobile
- `md:grid-cols-2`: Two columns on medium screens
- `lg:grid-cols-3`: Three columns on large screens
- `gap-8`: Spacing between grid items

## Fixing Broken Links

### Current Link Inventory
1. Navigation Menu Links:
```html
<a href="#features">Kenmerken</a>
<a href="#benefits">Voordelen</a>
<a href="#faq">FAQ</a>
<a href="https://nachtbril.com/shop">Bestel Nu</a>
```

To update internal links:
1. Find the section ID in the HTML:
```html
<section id="features">
```
2. Update the href to match:
```html
<a href="#features">
```

To update external links:
1. Locate the `href` attribute
2. Replace the URL:
```html
<!-- Before -->
<a href="https://nachtbril.com/shop">
<!-- After -->
<a href="https://your-shop-url.com">
```

## Adding Privacy and Terms Pages

### Footer Modification
Add privacy and terms links to the footer:

1. Locate the footer section:
```html
<footer class="bg-gray-900 text-white py-16">
    <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
```

2. Add new links:
```html
<div>
    <h3 class="text-xl font-bold mb-4">Legal</h3>
    <ul class="space-y-2">
        <li><a href="/privacy.html" class="hover:text-blue-400 transition-colors duration-300">Privacy Policy</a></li>
        <li><a href="/terms.html" class="hover:text-blue-400 transition-colors duration-300">Terms of Service</a></li>
    </ul>
</div>
```

3. Style consistency:
- Use `hover:text-blue-400` to match existing hover effects
- Add `transition-colors duration-300` for smooth color changes

## Troubleshooting

### Common Issues

1. **Broken Responsive Layout**
- Check for missing `md:` or `lg:` prefixes in classes
- Verify the viewport meta tag is present:
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

2. **Links Not Working**
- Ensure section IDs match href attributes exactly
- Check for typos in URLs
- Verify file paths for internal pages

3. **Styling Issues**
- Confirm Tailwind CSS is properly loaded
- Check for conflicting classes
- Verify class names are spelled correctly

### Need Help?
If you encounter issues:
1. Check the browser console for errors
2. Verify all files are in the correct directory
3. Test the page across different browsers
4. Ensure all external resources (CSS, JavaScript) are loading properly

Remember to:
- Back up your files before making changes
- Test all updates on a development environment first
- Validate your HTML using W3C Validator
- Check mobile responsiveness using browser dev tools