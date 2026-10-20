+++
title = "Page Options and Layouts"
description = "Customize individual Zolbare pages with per-page options and sidebar widgets."
date = 2026-10-13
authors = ["Vince"]

[taxonomies]
tags = ["configuration", "layout", "metadata"]
series = ["Making the Most of Zolbare"]

[extra]
order = 1

[[extra.widgets]]
title = "Configuration Resources"
items = [
    { name = "Zola Page Front Matter", url = "https://www.getzola.org/documentation/content/page/", out = true },
    { name = "Zola Configuration", url = "https://www.getzola.org/documentation/getting-started/configuration/", out = true },
    { name = "Theme Repository", url = "https://github.com/vincentdesiree/zolbare", out = true }
]
+++
Not every page needs the same layout. A long article benefits from a table of contents, while a short About page might work better without one.

Zolbare lets you customize individual pages through their front matter, without editing the theme templates.

## Control Metadata and Section Listings

You can control which metadata appears on individual pages and sections using the options below in `[extra]`. Section options can be set globally in `config.extra` and overridden per section, while page options are defined directly in each page's front matter.

| Option | Sections | Pages |
| :--- | :---: | :---: |
| `show_authors` | ✅ | ✅ |
| `show_dates` | ✅ | ✅ |
| `show_reading_time` | | ✅ |
| `show_description` | ✅ | |
| `show_toc` | | ✅ |
| `show_series` | ✅ | ✅ |
| `show_tags` | ✅ | ✅ |

For example, to hide the author and dates on a specific page:

```toml
[extra]
show_authors = false
show_dates = false
```

All options default to `true`. Section settings can be defined globally in `config.extra` and overridden at the section level, whereas page settings must be configured per page.

## Add sidebar widgets

You can also define widgets for an individual page. For example, add a set of useful links:

```toml
[[extra.widgets]]
title = "Useful Links"
items = [
    { name = "Zola Documentation", url = "https://www.getzola.org/documentation/", out = true },
    { name = "Theme Repository", url = "https://github.com/vincentdesiree/zolbare", out = true }
]
```

Each widget has a title and a list of links. The `out` field marks a link as external and opens it in a new tab.

You can add multiple widgets by repeating `[[extra.widgets]]`, each with its own title and items.

## Keep page-specific settings together

Here's what a page's front matter might look like with both options:

```toml
+++
title = "About"
description = "Learn more about Zolbare, a theme for websites powered by Zola."
date = 2026-10-13
authors = ["Vince"]

[extra]
show_toc = false

[[extra.widgets]]
title = "Project Links"
items = [
    { name = "GitHub", url = "https://github.com/vincentdesiree/zolbare", out = true }
]
+++
```

Keep in mind that these settings belong to the page, not the global site configuration.

## Recap: page-specific options

Zolbare lets you customize individual pages through their front matter:

* **Table of contents:** set `show_toc = false` to hide the TOC on a specific page.
* **Sidebar widgets:** add one or more `[[extra.widgets]]` entries, each with a title and a list of links.
* **External links:** use `out = true` on widget items to make external links.
* **Page metadata:** combine these options with the page's title, date, authors, taxonomies, and other front matter fields.

These settings apply to the page where they are defined, so different pages can have different TOC and sidebar configurations.
