# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Hugo theme called "movq" - a clean, minimal theme for static blog sites. The theme uses Georgia/Lato fonts and features a newspaper-like layout with centered content.

## Theme Architecture

### Layout Structure
- `layouts/baseof.html` - Base template with HTML structure and header/footer partials
- `layouts/home.html` - Homepage layout that displays site content and lists all regular pages
- `layouts/page.html` - Individual page layout
- Partials in `layouts/_partials/`:
  - `head.html` - Meta tags, title, and CSS/JS includes
  - `header.html` - Site header with navigation
  - `footer.html` - Site footer
  - `summary.html` - Post summary template for listings
  - `menu.html` - Navigation menu template
  - `terms.html` - Terms/taxonomy listing
  - `head/css.html` and `head/js.html` - Asset management

### Styling System
- Single CSS file: `assets/css/main.css` (337 lines)
- Typography: Georgia (serif) for body text, Lato (sans-serif) for headers
- Responsive design with mobile breakpoint at 550px
- Color scheme: Blue links (#2892ee), silver visited links (#b0beca), light gray backgrounds
- Content max-width: 650px, centered layout
- Article images are automatically centered

### Assets
- `assets/css/main.css` - Main stylesheet with complete theme styling
- `assets/js/main.js` - JavaScript functionality
- CSS uses Google Fonts for Lato font family

### Configuration
- `hugo.toml` - Theme configuration with menu structure
- Default menu items: Home (/), Posts (/posts), Tags (/tags)
- Hugo version requirement: 0.146.0+ (extended = false)
- `i18n/en.toml` - English language strings

## Key Features

### Typography & Layout
- Large header with site title (60pt on desktop, 30pt mobile)
- Article headers with blue timestamps and large titles
- Text indentation (1pc) for article content
- Bordered article footers with metadata
- Pagination support with styled navigation

### Responsive Design
- Mobile-first approach with desktop enhancement
- Header padding adjusts: 6pc desktop → 2pc mobile
- Font scaling: 60pt → 30pt for main title on mobile
- Content padding adapts for smaller screens

### Content Support
- Blog post listings with summary templates
- Tag/taxonomy pages
- Code syntax highlighting support
- Image centering and responsive sizing
- Blockquote styling with left border
- Table formatting with alternating rows

## Development Notes

- This is a Hugo theme repository, designed to be used as a submodule
- No build process required - Hugo processes assets directly
- CSS uses pt units for most spacing (picas: pc = 12pt)
- Layout uses Hugo's block system with baseof.html as foundation
- Partials are cached for performance (head/css.html, head/js.html)