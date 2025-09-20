# Movq Hugo Theme

A clean, minimal Hugo theme with a newspaper-like layout and typography. Originally ported from another framework, this theme focuses on readability and elegant content presentation.

## Features

- **Clean Typography**: Georgia serif body text with Lato sans-serif headers
- **Responsive Design**: Mobile-first approach with desktop enhancements
- **Pagination Support**: Configurable pagination for listings
- **SEO Optimized**: Built-in OpenGraph, Twitter Cards, and Schema.org structured data
- **Configurable Date Formats**: Customizable date display formats
- **Internationalization Ready**: Support for Hugo's i18n system
- **Asset Pipeline**: Minification and fingerprinting for CSS/JS in production
- **Schema.org Markup**: Structured data for articles and blog posts

## Installation

### As a Git Submodule (Recommended)

```bash
git submodule add https://github.com/yourusername/hugo-theme-movq.git themes/movq
```

### Download

Download the theme as a ZIP file and extract it to your `themes/movq` directory.

## Configuration

### Basic Configuration

Add the theme to your site's `hugo.toml`:

```toml
theme = "movq"
paginate = 10
paginatePath = "page"

[params]
  subtitle = "Your site subtitle"

[params.dateFormats]
  # Machine-readable date format for datetime attributes
  machine = "2006-01-02T15:04:05-07:00"
  # Human-readable date format for article listings and headers
  human = ":date_long"
  # Full date format for publish dates
  published = ":date_full"
```

### Menu Configuration

The theme supports Hugo's menu system:

```toml
[menus]
  [[menus.main]]
    name = 'Home'
    pageRef = '/'
    weight = 10

  [[menus.main]]
    name = 'Posts'
    pageRef = '/posts'
    weight = 20

  [[menus.main]]
    name = 'Tags'
    pageRef = '/tags'
    weight = 30
```

### Date Format Customization

Customize how dates appear throughout your site:

```toml
[params.dateFormats]
  # Use Hugo's localized formats
  human = ":date_medium"
  published = ":date_full"

  # Or use custom Go time formats
  human = "January 2, 2006"
  published = "Monday, January 2, 2006"
```

Available Hugo date formats:
- `:date_full` - Monday, January 2, 2006
- `:date_long` - January 2, 2006
- `:date_medium` - Jan 2, 2006
- `:date_short` - 1/2/06

### Social Media & SEO

The theme automatically generates OpenGraph, Twitter Cards, and Schema.org metadata. Configure your site information:

```toml
[params]
  description = "Your site description"
  images = ["featured-image.jpg"]  # Default image for social sharing

[social]
  twitter = "yourtwitterhandle"
```

## Content Organization

### Blog Posts

Create blog posts in the `content/posts/` directory:

```bash
hugo new posts/my-first-post.md
```

### Front Matter

Recommended front matter for posts:

```yaml
---
title: "My Blog Post"
date: 2024-01-15T10:00:00-07:00
lastmod: 2024-01-16T12:00:00-07:00
description: "A brief description of the post"
tags: ["hugo", "web", "blogging"]
images: ["featured-image.jpg"]
---
```

## Customization

### Typography

The theme uses a carefully chosen typography stack:

- **Body Text**: Georgia, "Times New Roman", serif
- **Headers**: 'Lato', 'Helvetica Neue', 'Helvetica', sans-serif

### Colors

Key color values used in the theme:

- **Primary Links**: `#2892ee`
- **Visited Links**: `#b0beca`
- **Background**: `#f5f5f5`
- **Text**: Default black/gray tones

### Layout

- **Content Width**: 650px maximum, centered
- **Responsive Breakpoint**: 550px for mobile styles
- **Spacing Unit**: Uses picas (pc) where 1pc = 12pt

### Custom CSS

To add custom styles, create `assets/css/custom.css` in your site root:

```css
/* Your custom styles */
.custom-class {
    color: #your-color;
}
```

Then import it in your site's CSS pipeline or add it to the theme.

## Internationalization

The theme includes English translations for pagination and date formatting. To add other languages, create translation files:

```toml
# i18n/fr.toml
[pagination_first]
other = "Premier"

[pagination_prev]
other = "‹ Précédent"

[pagination_next]
other = "Suivant ›"

[pagination_last]
other = "Dernier"
```

## Development

### Requirements

- Hugo v0.146.0 or later
- Hugo Extended version not required

### Local Development

```bash
# Start development server
hugo server -D

# Build for production
hugo --minify
```

### Theme Structure

```
layouts/
├── _default/
├── _partials/
│   ├── head.html
│   ├── header.html
│   ├── footer.html
│   ├── summary.html
│   ├── pagination.html
│   ├── dates.html
│   ├── terms.html
│   └── menu.html
├── baseof.html
├── home.html
├── page.html
├── section.html
├── term.html
└── taxonomy.html

assets/
├── css/
│   └── main.css
└── js/
    └── main.js
```

## Browser Support

The theme supports all modern browsers and degrades gracefully for older browsers. The responsive design works on:

- Desktop browsers (Chrome, Firefox, Safari, Edge)
- Mobile browsers (iOS Safari, Chrome Mobile, Samsung Internet)
- Tablet browsers

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This theme is released under the [MIT License](LICENSE).

## Credits

- Typography inspired by traditional newspaper design
- Built with [Hugo](https://gohugo.io/)
- Uses [Lato](https://fonts.google.com/specimen/Lato) font from Google Fonts