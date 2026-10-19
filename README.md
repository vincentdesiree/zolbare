# Zolbare

[![Demo](https://img.shields.io/badge/demo-online-brightgreen)](https://zolbare-demo.vincentdesiree.com)
[![GitHub Release](https://img.shields.io/github/v/release/vincentdesiree/zolbare?color=blue)](https://github.com/vincentdesiree/zolbare/releases/latest)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Zola](https://img.shields.io/badge/Zola-0.23%2B-orange)](https://www.getzola.org/)
[![CI Status](https://github.com/vincentdesiree/zolbare/actions/workflows/ci.yml/badge.svg)](https://github.com/vincentdesiree/zolbare/actions/workflows/ci.yml)

A lightweight, responsive theme for [Zola](https://www.getzola.org/), designed for content-focused websites with a clean layout and minimal dependencies.

**[Live demo and documentation](https://zolbare-demo.vincentdesiree.com/)**

## Features

- Responsive layout for desktop and mobile
- Automatic light and dark themes based on system preferences
- Table of contents for long-form content
- Configurable sidebars and link widgets
- Series and taxonomy navigation
- Per-page and per-section display options
- Markdown content with syntax-highlighted code blocks
- Vanilla CSS and no JavaScript required by the theme itself

Explore the live demo to see the available layouts, content features, and configuration options.

## Requirements

- [Zola](https://www.getzola.org/)

Check `theme.toml` for the minimum supported Zola version.

## Installation

### Option 1: Git

Clone the repository into your site's `themes` directory:

```bash
git clone https://github.com/vincentdesiree/zolbare.git themes/zolbare
```

### Option 2: Download

Download and extract the repository into your site's `themes/zolbare` directory.

You can download an archive from the [GitHub repository](https://github.com/vincentdesiree/zolbare).

## Configuration

Set the theme name in your site's `zola.toml`:

```toml
theme = "zolbare"
```

Start the local development server:

```bash
zola serve
```

Visit the local URL displayed by Zola to preview your site.

For available options and examples, see the [live demo and documentation](https://zolbare-demo.vincentdesiree.com/).

## Customization

Zolbare uses Zola's templates and front matter, with vanilla CSS for styling. You can customize page and section layouts, metadata visibility, and sidebar widgets through your site's configuration and content files.

Refer to the demo for practical examples before modifying the theme templates or stylesheets.

## Privacy

Zolbare does not require JavaScript or include its own analytics or tracking mechanisms by default. Your site's actual behavior may differ depending on your hosting provider, external resources, and any customizations you make.

Adapt your site's privacy notice to its actual configuration. The demo's privacy page provides a concrete example.

## Status

Zolbare **v0.1.0** is an initial usable release. Features and configuration may evolve as the theme develops.

## License

Zolbare is distributed under the [MIT License](LICENSE).
