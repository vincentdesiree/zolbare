+++
title = "Table of Contents and Long-Form Articles"
description = "Make long articles easier to navigate with Zolbare's responsive table of contents."
date = 2026-10-13
authors = ["Vince"]

[taxonomies]
tags = ["navigation", "toc", "writing"]
series = ["Making the Most of Zolbare"]

[extra]
order = 2

[[extra.widgets]]
title = "Reading Resources"
items = [
    { name = "Zola Table of Contents", url = "https://www.getzola.org/documentation/content/table-of-contents/", out = true },
    { name = "Markdown Guide", url = "https://www.markdownguide.org/basic-syntax/", out = true },
    { name = "Theme Repository", url = "https://github.com/vincentdesiree/zolbare", out = true }
]
+++
Long articles are useful, but scrolling through a wall of text to find one section isn't much fun.

That's why Zolbare includes a table of contents (TOC) for navigating longer pages.

## Desktop: keep navigation close

On desktop, the TOC sits in a sticky sidebar. It stays visible as you scroll, so you can jump between sections without losing your place.

The TOC follows the article's heading structure. Use headings to organize your content, and the navigation will be much more useful.

## Mobile: keep it compact

On smaller screens, the TOC is collapsible and sits near the top of the article.

It stays out of the way until the reader needs it. No oversized sidebar competing with the actual content.

## Structure your headings

Good headings make an article easier to scan and help readers understand how its sections fit together.

For example:

```markdown
## Getting Started

### Installation

### Configuration

## Customization

### Colors

### Typography
```

Heading levels determine the hierarchy displayed in the TOC.

## Hide the TOC when you don't need it

Short pages don't always benefit from a table of contents.

To disable it for an individual page, add this to the page's front matter:

```toml
[extra]
show_toc = false
```

For longer articles, leave the TOC enabled.

## Recap: table of contents

Zolbare's responsive TOC provides several navigation options:

* **Desktop:** a sticky sidebar keeps the TOC visible while scrolling.
* **Mobile:** a collapsible TOC sits near the top of the article.
* **Heading hierarchy:** the TOC is generated from the article's headings, including nested sections.
* **Per-page control:** set `show_toc = false` in `[extra]` to hide it on individual pages.

Markdown headings such as `## Section` and `### Subsection` define the structure used by the TOC.
