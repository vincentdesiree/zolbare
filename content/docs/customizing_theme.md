+++
title = "Customizing the Theme"
description = "Customize Zolbare's colors, layout, and typography with CSS, without editing its templates."
date = 2026-10-13
authors = ["Vince"]

[taxonomies]
tags = ["customization", "css", "design"]
series = ["Making the Most of Zolbare"]

[extra]
order = 5

[[extra.widgets]]
title = "CSS Resources"
items = [
{ name = "MDN CSS Reference", url = "https://developer.mozilla.org/en-US/docs/Web/CSS/Reference", out = true },
{ name = "MDN Media Queries", url = "https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries", out = true },
{ name = "Theme Repository", url = "https://github.com/vincentdesiree/zolbare", out = true }
]
+++

Zolbare's stylesheet defines the theme's colors, layout, typography, navigation, article content, widgets, and other components. CSS lets you customize these elements without changing the HTML templates.

## Change the colors

Zolbare uses CSS custom properties for its main colors. The default dark theme defines them in `:root`:

```css
:root {
    --bg: #121212;
    --card-bg: #1e1e1e;
    --border: #2a2a2a;
    --text: #e0e0e0;
    --muted: #a0a0a0;
    --accent: #de6432;
    --link: #66b2ff;
    --code-bg: #1d1f1d;
    --inline-code-bg: #2d2f2d;
```

These variables control different parts of the theme:

* `--bg`: page background
* `--card-bg`: navigation menu and widget backgrounds
* `--border`: borders around components
* `--text`: main text color
* `--muted`: secondary text, metadata, and dates
* `--accent`: accent color, including blockquote borders and pagination
* `--link`: links
* `--code-bg`: code block backgrounds
* `--inline-code-bg`: inline code backgrounds

For example, changing `--accent` changes the accent color wherever that variable is used.

## Customize light and dark themes

Zolbare supports light and dark color schemes based on the user's system preference. The light theme overrides the color variables inside a media query:

```css
@media (prefers-color-scheme: light) {
    :root {
        --bg: #ffffff;
        --card-bg: #f8f9fa;
        --border: #e9ecef;
        --text: #212529;
        --muted: #6c757d;
        --accent: #d9531e;
        --link: #0066cc;
        --code-bg: #f1f3f5;
        --inline-code-bg: #e1e3e5;
    }
}
```

You can replace these values to customize the light palette independently of the dark palette.

## Adjust the layout

Several variables control the overall layout:

```css
:root {
    --max-w: 1080px;
    --content-w: 75ch;
    --gutter: clamp(1rem, 4vw, 2rem);
}
```

* `--max-w` sets the maximum width of the header, footer, and main container.
* `--content-w` limits the width of article and section text.
* `--gutter` controls the horizontal padding around the page.

For example, to give article text more room:

```css
:root {
    --content-w: 85ch;
}
```

The main container also has its own spacing and minimum height:

```css
.main-container {
    min-height: 75vh;
    padding-block: 2rem;
}
```

## Change typography

Zolbare uses system fonts by default and defines responsive sizes for major headings:

```css
--font-h1: clamp(1.75rem, 4vw + 1rem, 2.5rem);
--font-h2: clamp(1.35rem, 2vw + 1rem, 1.75rem);
```

You can adjust these variables to change heading sizes across the theme. For example:

```css
:root {
    --font-h1: clamp(2rem, 4vw + 1rem, 3rem);
    --font-h2: clamp(1.5rem, 2vw + 1rem, 2rem);
}
```

The body font and line height are also configurable through the `body` selector:

```css
body {
    font-family: system-ui, sans-serif;
    line-height: 1.7;
}
```

Article titles use `.article-title`, while section headings and article-list headings use `.section-header h1` and `.list-article h2`. These selectors let you customize individual heading styles.

## Customize article content

The `.article-content` and `.section-content` selectors control the main reading area. For example, you can change the font size of both:

```css
.article-content,
.section-content {
    font-size: 1.1rem;
}
```

Other article elements have their own selectors:

* `blockquote` controls quotations, including their accent-colored left border.
* `pre` controls code block backgrounds, padding, horizontal scrolling, and font size.
* `.article-meta` controls the appearance of article metadata.
* `.tag-badge` controls the tags displayed in the article footer.

For example, to change code block sizing:

```css
pre {
    font-size: 1rem;
    border-radius: 8px;
}
```

## Customize navigation and widgets

Navigation, sidebars, and widgets also have dedicated selectors.

The navigation menu uses `.nav-content`, with separate styles for mobile and desktop layouts. Its desktop layout activates at `40rem`.

Article widgets use `.widget`, `.widget-title`, and `.widget-links`. For example, you can change their appearance:

```css
.widget {
    padding: 1.25rem;
    border-radius: 8px;
}

.widget-title {
    font-size: 1.1rem;
}
```

The article sidebar becomes sticky on wider screens, starting at `60rem`. At that breakpoint, the article layout can display the content and sidebar in separate columns.

## Recap: what CSS lets you customize

Zolbare's existing stylesheet provides selectors and variables for:

* **Colors:** backgrounds, text, links, borders, accents, and code blocks.
* **Layout:** overall width, reading width, page gutters, spacing, and sidebar layout.
* **Typography:** system fonts, line height, heading sizes, and metadata.
* **Content:** article text, lists, quotations, code blocks, tags, and pagination.
* **Navigation:** mobile menu, desktop navigation, and search field.
* **Widgets:** sidebar backgrounds, borders, titles, and links.
* **Responsive behavior:** layout changes at the existing `40rem` and `60rem` breakpoints.

These options cover much of the theme's visual appearance through CSS alone. Changes to the underlying HTML structure or template logic require editing the templates.
