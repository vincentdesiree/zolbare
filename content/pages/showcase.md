+++
title = "Markdown Showcase"
description = "A comprehensive showcase of Markdown, syntax highlighting, images, videos, tables, and HTML elements supported by Zolbare."
date = 2026-10-14
authors = ["Vince"]
path = "showcase"

[extra]
show_toc = true

[[extra.widgets]]
title = "Markdown Resources"
items = [
{ name = "Markdown Guide", url = "https://www.markdownguide.org/", out = true },
{ name = "CommonMark Spec", url = "https://commonmark.org/", out = true },
{ name = "GitHub Flavored Markdown", url = "https://github.github.com/gfm/", out = true },
{ name = "Zola Markdown", url = "https://www.getzola.org/documentation/content/syntax-highlighting/", out = true },
{ name = "Zolbare Repository", url = "https://github.com/vincentdesiree/zolbare", out = true }
]
+++

This page demonstrates how common Markdown elements, code blocks, images, videos, and embedded HTML are rendered by Zolbare.

It also serves as a practical test page for theme development. If you change the typography, spacing, responsive layouts, or syntax highlighting, this page provides a single place to check the results.

## 1. Text and inline formatting

Regular paragraph text demonstrates the default font, line height, paragraph spacing, and content width.

This paragraph contains **bold text**, *italic text*, ~~strikethrough text~~, and `inline code`. You can also combine **bold and *italic*** formatting.

Here is a [link to the Zola website](https://www.getzola.org/), a link to the [Zolbare repository](https://github.com/vincentdesiree/zolbare), and an example of an autolink: https://commonmark.org/.

A longer paragraph helps evaluate readability across multiple lines. Good typography should remain comfortable to read without making the content excessively wide. This paragraph also helps check how links, emphasis, and inline code behave when they appear in the middle of ordinary prose.

### Special characters

Markdown should handle characters such as `&`, `<`, `>`, `"`, `'`, and Unicode text without unexpected rendering.

Some examples: café, naïve, Ελληνικά, 日本語, and symbols such as ©, ™, →, and ±.

Inline HTML can also be tested with <kbd>Ctrl</kbd> + <kbd>C</kbd>, a subscript such as H<sub>2</sub>O, and a superscript such as x<sup>2</sup>.

## 2. Headings and document hierarchy

The page title is generated from the front matter. The headings below test the hierarchy used by the article layout and table of contents.

### Third-level heading

A third-level heading should be visually distinct from the main sections without competing with them.

#### Fourth-level heading

This level is useful for deeply structured documentation and tests whether the heading spacing and font sizes remain balanced.

##### Fifth-level heading

A fifth-level heading is less common, but it should still render predictably.

###### Sixth-level heading

The smallest Markdown heading completes the hierarchy test.

## 3. Lists

### Unordered lists

* First-level item
* Another item

  * Nested item
  * Another nested item

    * Third-level nested item
* Back to the first level

### Ordered lists

1. Install Zola.
2. Configure the site.
3. Add the theme.
4. Build the website.

### Ordered lists with nested items

1. Prepare the content.

   1. Create the page.
   2. Add front matter.
2. Configure the theme.

   1. Set the site title.
   2. Configure the navigation.
3. Build and test the site.

### Task lists

* [x] Create the page.
* [x] Add Markdown examples.
* [ ] Test the rendered page on mobile.
* [ ] Check all media and links.

Task-list syntax is an extension of Markdown; its rendering depends on the parser and enabled extensions.

### Lists with paragraphs

1. **First item**

   This item contains a second paragraph to test spacing and indentation.

2. **Second item**

   The next item should remain visually associated with its number, even when the content spans several lines.

## 4. Blockquotes

> This is a simple blockquote.
>
> It contains two paragraphs to test spacing within the quotation.

### Nested blockquotes

> This is the outer quotation.
>
> > This is a quotation nested inside it.
> >
> > It contains another paragraph.
>
> The outer quotation continues here.

### A quotation containing other elements

> **A quoted heading**
>
> A blockquote can contain *emphasis*, `inline code`, and a [link to Zola](https://www.getzola.org/).
>
> * A list inside a quotation
> * Another list item
>
> ```rust
> fn main() {
>     println!("Code inside a blockquote");
> }
> ```

## 5. Horizontal rules

The following examples test horizontal separators between sections.

---

A separator followed by a paragraph.

---

Another separator.

---

## 6. Tables

### Basic table

| Component             | Technology  |
| :-------------------- | :---------- |
| Static site generator | Zola        |
| Template engine       | Tera        |
| Styling               | Vanilla CSS |
| JavaScript            | None        |

### Alignment

| Left-aligned   |   Center-aligned   | Right-aligned |
| :------------- | :----------------: | ------------: |
| Text           |        Text        |           123 |
| Short          | Medium-length text |         4,567 |
| Longer content |    Another value   |        89,012 |

### A wider table

| Feature             | Description                        | Desktop |     Mobile     | Notes                       |
| :------------------ | :--------------------------------- | :-----: | :------------: | :-------------------------- |
| Table of contents   | Navigation generated from headings | Sidebar | Compact layout | Page option available       |
| Syntax highlighting | Colored source code                |   Yes   |       Yes      | Depends on language support |
| Responsive images   | Images fit their containers        |   Yes   |       Yes      | Check intrinsic dimensions  |
| External links      | Links to other websites            |   Yes   |       Yes      | Widget configuration        |
| Dark mode           | System color preference            |   Yes   |       Yes      | Native CSS media query      |

This table is deliberately wider than the first examples. Check its horizontal overflow and cell spacing on narrow screens.

## 7. Images

### Markdown image

![A landscape used to test image rendering](https://picsum.photos/id/1018/1000/600)

*Figure 1: A landscape image with alternative text and a caption.*

### Image with a link

[![A smaller landscape image](https://picsum.photos/id/1015/480/320)](https://picsum.photos/id/1015/1200/800)

Click the image to open its larger version.

### Image with HTML attributes

<img src="https://picsum.photos/id/1025/600/400" alt="A dog used to test HTML image attributes" width="600" loading="lazy">

This example tests whether raw HTML images render correctly and respect their width and lazy-loading attributes.

### Local images

To test local assets, place an image in the site's `static/` directory and reference it using its public URL:

```markdown
![Local test image](/og_image.png)
```
![Local test image](/og_image.png)

This is useful for checking image paths, deployment behavior, and whether local images work independently of third-party services.

## 8. Videos and embedded media

### HTML5 video

The following video uses an external MP4 file. It tests the native video player and responsive media sizing.

<video controls preload="metadata" width="640" poster="https://picsum.photos/id/1039/640/360">
  <source src="https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.mp4" type="video/mp4">
  Your browser does not support HTML5 video.
</video>

*Figure 2: Native HTML5 video with controls and a poster image.*

### Embedded video

An iframe tests embedded media and its behavior inside the article content.
<div class="video-embed">
    <iframe 
        src="https://www.youtube-nocookie.com/embed/aqz-KE-bpKQ"
        title="Sample embedded video"
        loading="lazy"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        referrerpolicy="strict-origin-when-cross-origin" 
        allowfullscreen>
    </iframe>
</div>

*Figure 3: An embedded video. External availability and browser policies may affect playback.*

### Local video

For a local video, put an MP4 file in `static/videos/` and use a URL such as `/videos/showcase.mp4`:

```html
<video controls preload="metadata" width="640">
  <source src="/videos/showcase.webm" type="video/webm">
  Your browser does not support HTML5 video.
</video>
```
<video controls preload="metadata" width="640">
  <source src="/videos/showcase.webm" type="video/webm">
  Your browser does not support HTML5 video.
</video>

This example can be used to test media hosted alongside the site rather than on an external service.

## 9. Inline code and code blocks

Inline code is useful for file names such as `zola.toml`, variables such as `show_toc`, and commands such as `zola build`.

### Plain text

```text
This is a plain text code block.
It should use the theme's code background and preserve whitespace.

    Indentation should remain visible.
```

### Bash

```bash
# Build the site
zola build

# Start the local development server
zola serve

# Check the generated output
find public -maxdepth 2 -type f
```

### TOML

```toml
title = "Zolbare Demo"
description = "A minimalist Zola theme"
base_url = "https://example.com"

[markdown]
highlight_code = true

[extra]
show_toc = true
```

### JSON

```json
{
  "name": "zolbare",
  "description": "A minimalist theme for Zola",
  "features": [
    "responsive layout",
    "dark mode",
    "syntax highlighting"
  ],
  "javascript": false
}
```

### JavaScript

```javascript
function greet(name) {
    const message = `Hello, ${name}!`;
    console.log(message);
    return message;
}

greet("Zolbare");
```

### CSS

```css
:root {
    --bg: #121212;
    --text: #e0e0e0;
    --accent: #de6432;
}

.article-content {
    max-width: 75ch;
    line-height: 1.6;
}
```

### HTML

```html
<article>
  <h2>Example article</h2>
  <p>A paragraph with <strong>semantic markup</strong>.</p>
  <a href="https://www.getzola.org/">Visit Zola</a>
</article>
```

### Rust

```rust
use std::collections::HashMap;

fn word_counts(text: &str) -> HashMap<&str, usize> {
    let mut counts = HashMap::new();

    for word in text.split_whitespace() {
        *counts.entry(word).or_insert(0) += 1;
    }

    counts
}

fn main() {
    let text = "rust is fast and rust is reliable";
    let counts = word_counts(text);

    println!("{counts:#?}");
}
```

### Python

```python
from collections import Counter

def word_counts(text: str) -> Counter:
    return Counter(text.split())

text = "python makes this example easy to read"
print(word_counts(text))
```

### Diff

```diff
- let theme = "old-theme";
+ let theme = "zolbare";

- show_toc = true
+ show_toc = false
```

## 10. Line numbers and highlighted lines

Zolbare uses Zola's configured syntax-highlighting system. The examples below test line numbers, custom starting numbers, and highlighted lines.

### Line numbers

```rust,linenos
fn main() {
    let theme = "Zolbare";
    println!("Welcome to {theme}");
}
```

### Custom starting line

```rust,linenos,linenostart=10
fn configure_theme() {
    let dark_mode = true;
    let responsive = true;

    println!("Dark mode: {dark_mode}");
    println!("Responsive: {responsive}");
}
```

### Highlighted lines

```rust,linenos,hl_lines=2 4
fn main() {
    let important = true;
    let optional = false;
    println!("Important: {important}");
}
```

Check that line numbering remains aligned, highlighted lines are distinguishable in both color schemes, and horizontal scrolling does not break the layout.

## 11. Links and reference-style links

A [normal inline link](https://www.getzola.org/) can appear within a sentence.

Reference-style links can make longer Markdown documents easier to maintain. For example, see the [Markdown Guide][markdown-guide] or the [CommonMark specification][commonmark].

[markdown-guide]: https://www.markdownguide.org/
[commonmark]: https://commonmark.org/

You can also link to a local page such as the [About page](/about/) or return to the [home page](/).

## 12. Raw HTML

Markdown documents can contain HTML when the parser and site configuration allow it.

### Details and summary

<details>
  <summary>Click to expand this section</summary>

This content is inside a native HTML disclosure element.

It can contain **formatted text**, links, and other HTML elements.

```rust
fn main() {
    println!("Hidden code example");
}
```

</details>

### Keyboard input

Press <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd> to open a command palette in applications that support this shortcut.

### Progress element

<progress value="70" max="100">70%</progress>

### Abbreviation

<abbr title="Static Site Generator">SSG</abbr> stands for Static Site Generator.

These elements are included to test raw HTML handling and browser-native rendering, not to imply that every element needs custom theme styling.

## 13. Footnotes

Here is a sentence with a footnote reference.[^first]

Here is another sentence with a second footnote.[^second]

[^first]: This footnote tests whether the Markdown parser supports footnotes and how the generated reference and footnote section are styled.

[^second]: Footnote rendering may depend on the Markdown extensions enabled in the Zola configuration.

## 14. Long content and wrapping

This paragraph contains a deliberately long URL to test overflow handling: https://example.com/a/very/long/path/used/to/check/how/long/links/behave/inside/a/narrow/article/container/without/causing/horizontal/page/overflow.

The following line tests a long unbroken string:

`supercalifragilisticexpialidocious_supercalifragilisticexpialidocious_supercalifragilisticexpialidocious`

The article should remain readable on narrow screens. Long code lines, URLs, tables, images, and embedded media should not create unwanted horizontal overflow across the entire page.

## 15. Final checklist

Use this page when testing theme changes:

* [ ] Typography and paragraph spacing
* [ ] Heading sizes and hierarchy
* [ ] Table of contents and anchor links
* [ ] Nested lists and blockquotes
* [ ] Table borders, alignment, and cell spacing
* [ ] Inline code and syntax highlighting
* [ ] Line numbers and highlighted lines
* [ ] Image sizing, captions, and alternative text
* [ ] Video controls and iframe sizing
* [ ] Raw HTML elements
* [ ] Light and dark color schemes
* [ ] Mobile layout and horizontal overflow
* [ ] Links, focus states, and keyboard navigation

Some examples rely on external resources or optional Markdown extensions. A failed external embed does not necessarily indicate a theme bug; check the URL, browser policies, and parser configuration first.
