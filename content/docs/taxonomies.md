+++
title = "Organizing Content with Tags and Series"
description = "Use Zola taxonomies and Zolbare's series navigation to connect related articles."
date = 2026-10-13
authors = ["Vince"]

[taxonomies]
tags = ["taxonomy", "organization", "series"]
series = ["Making the Most of Zolbare"]

[extra]
order = 3

[[extra.widgets]]
title = "Taxonomy Resources"
items = [
  { name = "Zola Taxonomies", url = "https://www.getzola.org/documentation/content/taxonomies/", out = true },
  { name = "Zola Content Overview", url = "https://www.getzola.org/documentation/content/overview/", out = true },
  { name = "Theme Repository", url = "https://github.com/vincentdesiree/zolbare", out = true }
]
+++
As your site grows, readers need ways to find related content. Zola's taxonomies let you organize pages without adding a database or a plugin.

Zolbare uses tags and series for two different purposes.

## Tags: group related topics

Tags connect articles that cover similar subjects, even when those articles belong to different series.

Add tags to a page's front matter:

```toml
[taxonomies]
tags = ["zola", "configuration", "layout"]
```

Zola generates taxonomy pages where readers can browse content associated with each tag.

Keep your vocabulary consistent. For example, using both `customization` and `customizing` for the same topic can split related articles across separate pages.

A small, useful set of tags is better than a long list of near-duplicates.

## Series: connect articles in a sequence

A series groups articles that belong together, such as a set of tutorials.

Add the series name to the page's taxonomies:

```toml
[taxonomies]
tags = ["zola", "configuration"]
series = ["Making the Most of Zolbare"]
```

Use the same series name across all articles in that series.

## Set the order manually

Taxonomy pages don't necessarily reflect the reading order you want for a tutorial. Zolbare uses `extra.order` to define that order explicitly.

For example, the first article in this series has:

```toml
[extra]
order = 1
```

The next article uses `order = 2`, then `order = 3`, and so on.

Keep the number consistent with the intended position in the series. This lets readers follow the sequence even when article titles don't sort alphabetically.

## Put it together

A complete front matter example:

```toml
+++
title = "Page Options and Layouts"
date = 2026-10-13
authors = ["Vince"]

[taxonomies]
tags = ["configuration", "layout", "metadata"]
series = ["Making the Most of Zolbare"]

[extra]
order = 1
+++
```

Each part has a job:

* **Tags** connect articles by topic.
* **Series** connect articles that belong together.
* **Order** defines the reading sequence within a series.

## Recap: organizing content

Zola taxonomies and Zolbare's series navigation offer three ways to connect content:

* **Tags:** group articles by topic and generate taxonomy pages for browsing related content.
* **Series:** associate articles that belong to the same sequence using a shared series name.
* **Manual ordering:** set `extra.order` to define each article's position in a series.

Tags can connect articles across different series, while series navigation connects articles under a shared name and follows their configured order.
