# CLAUDE Development Guidelines for WordSen Website

## Project Overview
**Platform**: Jekyll 4.x with GitHub Pages  
**Hosting**: GitHub Pages (github-pages gem)  
**Theme**: Custom (no third-party theme dependency)  
**Architecture**: Static site generator with Liquid templating  

## Development Principles

### Code Quality & Architecture
- **DRY (Don't Repeat Yourself)**: Use Jekyll includes, layouts, and data files to avoid code duplication
- **SOLID Principles**: Maintain single responsibility in components, open for extension via Jekyll's plugin system
- **Modern CSS**: Use CSS custom properties (variables), logical properties, and container queries where appropriate
- **Performance-First**: Optimize for Core Web Vitals, lazy loading, and minimal JavaScript

### Responsive Design Standards
- **Mobile-First Approach**: Design for mobile, enhance for desktop
- **Breakpoints**: 
  - Mobile: < 768px
  - Tablet: 768px - 1024px  
  - Desktop: > 1024px
- **Fluid Typography**: Use `clamp()` for responsive font sizes
- **Flexible Layouts**: CSS Grid and Flexbox for adaptive layouts

## File Structure & Organization

```
├── _config.yml              # Jekyll configuration
├── _includes/               # Reusable HTML components
│   ├── header.html
│   ├── footer.html
│   └── meta.html
├── _layouts/                # Page templates
│   ├── default.html         # Base layout
│   ├── home.html           # Homepage layout
│   └── post.html           # Blog post layout
├── _sass/                   # SCSS partials
│   ├── main.scss           # Main stylesheet
│   ├── _variables.scss     # CSS custom properties
│   ├── _components.scss    # Component styles
│   └── _utilities.scss     # Utility classes
├── assets/
│   ├── css/                # Generated CSS
│   ├── js/                 # JavaScript files
│   └── images/             # Optimized images
├── _posts/                 # Blog posts (markdown)
└── _data/                  # Data files (YAML/JSON)
```

## CSS Architecture Guidelines

### CSS Custom Properties & Color Palette

#### **Color System**
```scss
:root {
  // Primary Colors
  --accent-color: #dd6245;        // Main brand color (warm red-orange)
  --accent-hover: #c54d30;        // Hover state for accent
  
  // Background Colors
  --light-bg: #f4f5f6;          // Default page backgrounds  
  --card-bg: #ffffff;           // Standout elements (cards, forms, callouts)
  --white: #ffffff;             // Pure white for contrast
  
  // Gradients (unchanged)
  --primary-gradient: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
  --secondary-gradient: linear-gradient(135deg, #d299c2 0%, #fef9d7 100%);
  --hero-gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  
  // Text Colors
  --text-dark: #2d3748;         // Headings and primary text
  --text-medium: #4a5568;       // Body text and descriptions
  --text-light: #718096;        // Secondary/muted text
}
```

#### **Color Usage Guidelines**

**Backgrounds:**
- `--light-bg (#f4f5f6)`: Use for page backgrounds, section backgrounds
- `--card-bg (#ffffff)`: Use for cards, forms, callouts, any element that needs to stand out
- **Gradients**: Keep unchanged for hero sections and decorative backgrounds

**Interactive Elements:**
- `--accent-color (#dd6245)`: Primary buttons, links, highlights, active states
- `--accent-hover (#c54d30)`: Hover states for interactive elements

**Examples:**
```scss
// Page section
.features-section { 
  background: var(--light-bg);  // Light gray background
}

// Standout card
.feature-card { 
  background: var(--card-bg);   // Pure white to stand out
}

// Button
.btn-primary { 
  background: var(--accent-color);  // Brand color
  &:hover { background: var(--accent-hover); }
}
```

### Component-Based CSS
- Use BEM methodology for class naming
- Scope styles to avoid global pollution  
- Leverage CSS nesting (native or SCSS)
- Use container queries for truly responsive components

### Performance Optimization
- **Critical CSS**: Inline above-the-fold styles
- **Web Fonts**: Use `font-display: swap` and preconnect
- **Image Optimization**: WebP format with fallbacks, proper sizing
- **CSS Minification**: Automatic via Jekyll build process

## JavaScript Standards

### Modern JavaScript (ES2024)
- Use native modules where possible
- Prefer `const` and `let` over `var`
- Utilize modern APIs: Intersection Observer, ResizeObserver
- Implement proper error handling and graceful degradation

### Current JavaScript Architecture
```javascript
// Event delegation pattern (current implementation is good)
document.addEventListener('DOMContentLoaded', function() {
  // Initialize components
});

// Consider upgrading to:
class MobileNav {
  constructor(toggleSelector, menuSelector) {
    this.toggle = document.querySelector(toggleSelector);
    this.menu = document.querySelector(menuSelector);
    this.init();
  }
  
  init() {
    if (!this.toggle || !this.menu) return;
    this.bindEvents();
  }
  
  bindEvents() {
    // Event binding logic
  }
}
```

## Jekyll-Specific Best Practices

### Liquid Templates
- Use descriptive variable names
- Implement proper error handling with `default` filters
- Cache expensive operations with `assign` or `capture`
- Use `where` and `sort` filters for data manipulation

### Front Matter Standards
```yaml
---
layout: default
title: "Page Title | WordSen"
description: "SEO-optimized description under 160 characters"
canonical_url: "https://www.wordsen.com/page"
og_image: "/assets/images/og-image.jpg"
date: 2025-08-29
modified_date: 2025-08-29
---
```

### SEO & Performance
- Implement structured data (JSON-LD)
- Use semantic HTML5 elements
- Optimize for accessibility (WCAG 2.1 AA)
- Generate XML sitemap and robots.txt
- Implement proper meta tags via includes

## GitHub Pages Deployment

### Build Configuration
```yaml
# _config.yml optimizations
plugins:
  - jekyll-feed
  - jekyll-sitemap
  - jekyll-seo-tag

# Performance settings
incremental: true
highlighter: rouge
markdown: kramdown
kramdown:
  input: GFM
  syntax_highlighter: rouge

# Security
safe: true
```

### Development Workflow
1. **Local Development**: `bundle exec jekyll serve --incremental`
2. **Testing**: Validate HTML, check accessibility, test responsive design  
3. **Deployment**: Automatic via GitHub Actions on push to main
4. **Monitoring**: Google PageSpeed Insights, Core Web Vitals

## Testing & Quality Assurance

### Tools to Use
- **HTML Validation**: W3C Markup Validator
- **Accessibility**: axe-core, WAVE
- **Performance**: Lighthouse, PageSpeed Insights  
- **Cross-Browser**: BrowserStack or similar
- **Mobile Testing**: Chrome DevTools device emulation

### Pre-Deploy Checklist
- [ ] HTML validates without errors
- [ ] CSS follows established patterns
- [ ] Images are optimized (WebP with fallbacks)
- [ ] Accessibility score > 95
- [ ] Performance score > 90
- [ ] Mobile-responsive on all breakpoints
- [ ] SEO meta tags present and accurate

## 2025 Modern Web Standards

### Progressive Enhancement
- Core functionality works without JavaScript
- Enhanced experience with JavaScript enabled
- Graceful degradation for older browsers

### Web Performance
- **Core Web Vitals**: LCP < 2.5s, FID < 100ms, CLS < 0.1
- **Bundle Size**: Keep JavaScript under 50KB gzipped
- **Image Optimization**: Lazy loading, proper sizing, modern formats

### Security
- **Content Security Policy**: Implement via meta tags
- **HTTPS Only**: Ensure all resources load over HTTPS
- **Dependency Management**: Regular security updates via Dependabot

### Accessibility (WCAG 2.1 AA)
- Semantic HTML structure
- Proper heading hierarchy
- Alt text for all images  
- Keyboard navigation support
- Color contrast ratios > 4.5:1

## Commands & Scripts

### Development
```bash
# Install dependencies  
bundle install

# Start development server
bundle exec jekyll serve --incremental

# Build for production
bundle exec jekyll build

# Update gems
bundle update
```

### Quality Checks
```bash
# HTML validation (install html-proofer)
bundle exec htmlproofer ./_site --check-html --check-opengraph

# Check for broken links
bundle exec htmlproofer ./_site --check-external-hash --check-favicon
```

## Future Enhancements

### Progressive Web App (PWA)
- Service worker for offline capability
- Web app manifest
- Push notifications for blog updates

### Advanced Performance
- Critical CSS extraction
- Code splitting for JavaScript
- Image lazy loading with intersection observer

### Analytics & Monitoring
- Google Analytics 4 implementation
- Real User Monitoring (RUM)
- Error tracking with Sentry

---

**Last Updated**: August 29, 2025  
**Jekyll Version**: 4.x  
**Ruby Version**: 3.x  
**Node Version**: 18.x (for any build tools)

## Notes for Claude
- Always validate HTML after making changes
- Test responsive design on multiple screen sizes
- Prioritize accessibility in all implementations  
- Keep the existing design system and CSS architecture
- Use Jekyll's built-in features before adding external dependencies
- All changes should maintain the site's performance scores