# Technical Documentation

## Project Architecture

This document provides technical details about the portfolio website's implementation, design decisions, and code organization.

---

## File Structure

```
portfolio/
├── index.html          # Main HTML document
├── css/
│   └── styles.css      # All styles (variables, layout, components, responsive)
├── js/
│   └── script.js       # Theme toggle functionality
├── assets/
│   └── images/         # Profile picture and project screenshots
├── docs/
│   ├── ai-usage-report.md
│   └── technical-documentation.md
└── README.md
```

---

## HTML Structure

### Document Outline

```
<!DOCTYPE html>
<html lang="en">
├── <head>           # Metadata, fonts, stylesheets
└── <body>
    ├── <header>     # Navigation and theme toggle
    ├── <main>
    │   ├── #about          # Introduction section
    │   ├── #skills         # Skills grid
    │   ├── #projects       # Project cards
    │   ├── #certifications # Certifications list
    │   └── #contact        # Contact form
    └── <footer>     # Links and copyright
```

### Semantic Elements Used

| Element | Purpose |
|---------|---------|
| `<header>` | Contains site navigation and branding |
| `<nav>` | Navigation menu |
| `<main>` | Primary content container |
| `<section>` | Thematic content groupings |
| `<footer>` | Site footer with links |
| `<form>` | Contact form |

### Accessibility Features

- `lang="en"` on `<html>` for screen readers
- `aria-label` on icon buttons
- `<label>` elements linked to inputs via `for` attribute
- `alt` attributes on all images
- Semantic heading hierarchy (`h1` → `h2` → `h3`)

---

## CSS Architecture

### Design System (CSS Variables)

Variables are defined in `:root` for easy theming and consistency:

```css
:root {
    /* Colors */
    --primary-color: #2563eb;
    --bg-color: #ffffff;
    --text-color: #1e293b;
    --text-muted: #64748b;
    
    /* Spacing */
    --section-padding: 5rem;
    --container-width: 1100px;
    --border-radius: 8px;
}
```

### Dark Theme Implementation

Dark theme uses the `[data-theme="dark"]` attribute selector:

```css
[data-theme="dark"] {
    --bg-color: #0f172a;
    --text-color: #f1f5f9;
    /* ... other overrides */
}
```

This approach allows theme switching by simply toggling a `data-theme` attribute on the `<html>` element, with all colors automatically updating.

### Layout Systems

**Flexbox** — Used for:
- Header layout (logo left, nav center, toggle right)
- Navigation links
- Certification items
- Centering content

**CSS Grid** — Used for:
- Skills cards (`grid-template-columns: repeat(auto-fit, minmax(280px, 1fr))`)
- Project cards (`grid-template-columns: repeat(auto-fit, minmax(320px, 1fr))`)

The `auto-fit` with `minmax()` creates a responsive grid that automatically adjusts columns based on viewport width.

### Responsive Breakpoints

| Breakpoint | Target | Key Changes |
|------------|--------|-------------|
| Default | Mobile (< 480px) | Single column, reduced spacing |
| 480px+ | Large mobile | Slightly increased spacing |
| 768px+ | Tablet | Two-column layouts, larger text |
| 1024px+ | Desktop | Full layout, max-width container |

Mobile-first approach: base styles are for mobile, `@media (min-width: ...)` adds complexity for larger screens.

### Component Styles

**Cards** (`.project-card`, `.skill-category`, `.cert-item`)
- Consistent border radius and shadows
- Hover effects with `transform` and `box-shadow`
- Smooth transitions (0.2s ease)

**Buttons**
- Primary color background
- Hover state with darker shade
- Active state removes transform for tactile feedback

**Form Inputs**
- Consistent padding and border
- Focus state with primary color border and subtle shadow
- Placeholder styling

---

## JavaScript Implementation

### Theme Toggle System

```
┌─────────────┐     ┌──────────────┐     ┌─────────────┐
│  Page Load  │ ──► │  initTheme() │ ──► │ Apply Theme │
└─────────────┘     └──────────────┘     └─────────────┘
                           │
                           ▼
                    ┌──────────────┐
                    │ Check Order: │
                    │ 1. localStorage
                    │ 2. System pref
                    │ 3. Default light
                    └──────────────┘

┌─────────────┐     ┌───────────────┐     ┌─────────────┐
│ Button Click│ ──► │ toggleTheme() │ ──► │ Apply Theme │
└─────────────┘     └───────────────┘     │ Save to LS  │
                                          └─────────────┘
```

### Key Functions

| Function | Purpose |
|----------|---------|
| `initTheme()` | Runs on page load, determines initial theme |
| `toggleTheme()` | Switches between light and dark |
| `applyTheme(theme)` | Sets `data-theme` attribute and updates button icon |
| `getStoredTheme()` | Retrieves preference from localStorage |
| `setStoredTheme(theme)` | Saves preference to localStorage |

### localStorage Usage

```javascript
// Save
localStorage.setItem('theme', 'dark');

// Retrieve
const theme = localStorage.getItem('theme'); // Returns 'dark' or null

// This persists across browser sessions
```

### System Preference Detection

```javascript
// Check if user prefers dark mode at OS level
window.matchMedia('(prefers-color-scheme: dark)').matches

// Listen for changes (e.g., user changes OS setting)
window.matchMedia('(prefers-color-scheme: dark)')
    .addEventListener('change', callback);
```

---

## Performance Considerations

### Optimizations Applied

1. **Minimal Dependencies** — No external frameworks, only Google Fonts
2. **CSS Transitions** — Used sparingly (only on interactive elements)
3. **Efficient Selectors** — Class-based selectors for performance
4. **Single JS File** — Minimal, focused functionality

### Loading Strategy

- CSS loaded in `<head>` to prevent FOUC (Flash of Unstyled Content)
- JavaScript loaded at end of `<body>` to not block rendering
- Google Fonts loaded with `display=swap` for text visibility during load

---

## Browser Compatibility

### Tested Browsers

- Chrome 120+
- Firefox 120+
- Safari 17+
- Edge 120+

### Features & Support

| Feature | Support |
|---------|---------|
| CSS Grid | All modern browsers |
| CSS Variables | All modern browsers |
| Flexbox | All modern browsers |
| localStorage | All modern browsers |
| `prefers-color-scheme` | All modern browsers |

---

## Future Improvements

Potential enhancements for future assignments:

1. **Form Backend** — Connect contact form to email service or database
2. **Animations** — Add scroll-triggered animations with Intersection Observer
3. **Project Filtering** — Filter projects by technology
4. **Blog Section** — Add blog or articles section
5. **Performance** — Add lazy loading for images
6. **PWA** — Convert to Progressive Web App with offline support

---

## Development Setup

### Requirements

- Modern web browser
- Code editor
- Live Server extension (for development)

### VS Code Extensions Recommended

- Live Server
- Prettier (code formatting)
- HTML CSS Support
- Auto Rename Tag

### Commands

```bash
# Clone repository
git clone [repository-url]

# No build process required - open index.html directly
# Or use Live Server for development
```

---

## Code Standards

### HTML
- 4-space indentation
- Lowercase tag names
- Double quotes for attributes
- Self-closing tags for void elements

### CSS
- BEM-inspired naming (`.component-element`)
- Logical property grouping
- Comments for major sections

### JavaScript
- camelCase for variables and functions
- Descriptive function names
- Comments for complex logic
