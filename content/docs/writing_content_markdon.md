+++
title = "Writing Content with Markdown"
description = "Learn the Markdown basics for writing clean, readable content with Zola and Zolbare."
date = 2026-10-03
authors = ["Vince"]

[ taxonomies ]
tags = ["zola", "markdown", "content"]
series = ["Getting Started with Zolbare"]

[extra]
order = 3

[[extra.widgets]]
title = "Writing Resources"
items = [
  { name = "Markdown Syntax", url = "https://www.markdownguide.org/basic-syntax/", out = true },
  { name = "GitHub Flavored Markdown", url = "https://github.github.com/gfm/", out = true  },
  { name = "Zola Content", url = "https://www.getzola.org/documentation/content/overview/", out = true },
]
+++
One of the nice things about Zola is that you can write your content in plain Markdown. No HTML templates to edit just to publish an article.

Create a `.md` file in your `content/` directory and start writing.

## A basic page

Every page can start with a TOML front matter block:

```toml
+++
title = "My First Article"
description = "A short description of this page."
+++
```

Write your Markdown below the closing `+++`.

## The basics

### Headings

Use `#` for headings. Add more `#` characters for lower levels:

```markdown
## A section

### A subsection
```

### Emphasis

```markdown
**Bold text**

*Italic text*
```

### Lists

Unordered lists use hyphens:

```markdown
- First item
- Second item
- Third item
```

Ordered lists use numbers:

```markdown
1. First step
2. Second step
3. Third step
```

### Links and images

```markdown
[Zola](https://www.getzola.org/)

![A descriptive image caption](/images/example.jpg)
```

Place the image at `static/images/example.jpg` so Zola can serve it from `/images/example.jpg`.

### Code

Inline code uses backticks:

```markdown
Run `zola build` to generate your site.
```

For a code block, use triple backticks and specify the language:

````markdown
```rust
fn main() {
    println!("Hello, Zolbare!");
}
```
````

Zola supports syntax highlighting for code blocks when configured. Check the Zola documentation if you want to customize its highlighting settings.

### Quotes

Use `>` to create a blockquote:

```markdown
> Keep it simple. Write good content.
```

## Tags and series

You can organize pages with taxonomies in the front matter, provided they're configured in `zola.toml`.

For example:

```toml
[ taxonomies ]
tags = ["markdown", "zola"]
series = ["Getting Started with Zolbare"]
```

Tags help readers find related content. A series groups articles that belong together.

## Keep it readable

A few simple habits go a long way:

* Use headings to break up long articles.
* Write descriptive link text.
* Add alternative text to meaningful images.
* Keep paragraphs short enough to scan comfortably.
* Use code blocks for commands and source code.

That's all you need to get started. Write in Markdown, let Zola build the site, and let Zolbare take care of the presentation.
