# Boston Web Design Landing Page - Maintenance Guide

This guide will help you maintain and customize the Boston Web Design landing page. It's written for beginners with no prior coding experience.

## Table of Contents
- [Updating Text and Styling](#updating-text-and-styling)
- [Managing Links](#managing-links)
- [Adding Privacy and Terms Pages](#adding-privacy-and-terms-pages)
- [Troubleshooting](#troubleshooting)

## Updating Text and Styling

### Header Section
The header contains the logo and navigation menu. To modify:

1. **Logo Text**: Find this line and change "BWD":
```html
<a href="/" class="text-2xl font-bold text-blue-600">BWD</a>
```

2. **Navigation Items**: Located in the header's `div` with class `md:flex`. Each link follows this pattern:
```html
<a href="#features" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">Features</a>
```

### Hero Section
The main headline and subtitle are in the first `section` after `<main>`:

```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 mb-6">Boston Web Design</h1>
<p class="text-xl md:text-2xl text-gray-600 mb-12">Best Websites In Boston</p>
```

#### Understanding Tailwind Classes Here:
- `text-4xl`: Large text on mobile
- `md:text-5xl`: Larger text on medium screens
- `lg:text-6xl`: Largest text on large screens
- `mb-6`: Margin bottom spacing

### Features Section
Each feature card follows this structure:
```html
<div class="bg-white p-8 rounded-2xl shadow-lg hover:shadow-xl transition-shadow duration-300">
    <div class="text-blue-600 mb-4">
        <!-- SVG icon here -->
    </div>
    <h3 class="text-xl font-semibold mb-4">Feature Title</h3>
    <p class="text-gray-600">Feature description text.</p>
</div>
```

## Managing Links

### Navigation Menu Links
Current internal links in the navigation:
- `#features`
- `#benefits`
- `#faq`
- `#contact`

To update these:
1. Locate the navigation `div` in the header
2. Change the `href` attribute to your desired destination
3. Update the corresponding text

Example:
```html
<!-- Original -->
<a href="#features" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">Features</a>

<!-- Modified -->
<a href="#services" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">Services</a>
```

### External Links
The page contains these external links that need updating:
1. Main CTA button:
```html
<a href="https://bwd.com" class="inline-block bg-blue-600 text-white px-8 py-4 rounded-lg">Get Started Today</a>
```

2. Email address:
```html
<a href="mailto:admin@bwd.com" class="text-lg hover:underline">admin@bwd.com</a>
```

## Adding Privacy and Terms Pages

### Footer Modification
Add privacy and terms links in the footer's Company section:

1. Locate this section in the footer:
```html
<div>
    <h4 class="text-white text-lg font-semibold mb-4">Company</h4>
    <ul class="space-y-2">
        <li><a href="#" class="hover:text-white transition-colors duration-300">About</a></li>
        <!-- Add new links here -->
    </ul>
</div>
```

2. Add the new links:
```html
<li><a href="/privacy.html" class="hover:text-white transition-colors duration-300">Privacy Policy</a></li>
<li><a href="/terms.html" class="hover:text-white transition-colors duration-300">Terms of Service</a></li>
```

3. Ensure the links match your file structure:
- If pages are in the root directory: `/privacy.html`
- If in a subdirectory: `/pages/privacy.html`

## Troubleshooting

### Common Issues

1. **Broken Links**
- Check that all `href` attributes point to valid URLs
- Verify file paths are correct
- Test all links after updating

2. **Responsive Design**
If elements look wrong on mobile:
- Ensure you keep the `md:` and `lg:` prefixed classes
- Don't remove the `container` class from parent divs
- Maintain the existing grid structure in sections

3. **Style Changes**
When updating Tailwind classes:
- Keep the `transition-` classes for smooth animations
- Maintain the `hover:` classes for interactive elements
- Don't remove responsive design classes (`md:`, `lg:`)

### Need Help?
- Review the [Tailwind CSS documentation](https://tailwindcss.com/docs)
- Test all changes in multiple browsers
- Use browser developer tools to inspect elements

Remember to:
- Back up the original file before making changes
- Test all modifications on a development environment first
- Validate all links before pushing to production
- Keep the responsive design intact by maintaining breakpoint classes