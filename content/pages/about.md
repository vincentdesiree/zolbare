+++
title = "About"
description = "Design principles and technical details of the Zolbare theme."
path = "about"

[extra]
show_toc = false
show_authors = false
show_reading_time = false
+++

Zolbare is a minimalist theme for Zola, designed for developers and writers who value simplicity, performance, and maintainability.

## Core Tech Stack

| Component                 | Technology                                 |
| :------------------------ | :----------------------------------------- |
| **Static site generator** | Zola                                       |
| **Styling**               | Vanilla CSS, CSS variables, native nesting |
| **Templates**             | Tera                                       |
| **JavaScript**            | None                                       |

## Design Philosophy

Zolbare keeps its implementation simple and relies on browser-native features rather than a JavaScript framework or a CSS build pipeline.

1. **Native browser features:** Uses `prefers-color-scheme` for color scheme preferences, native lazy loading for images where applicable, and CSS Grid and Flexbox for layouts.
2. **Semantic HTML:** Uses elements such as `<article>`, `<header>`, `<main>`, and `<footer>` to provide a clear document structure.
3. **Maintainable styling:** Uses CSS variables for shared design tokens, making colors, typography, and layout dimensions easier to customize.
