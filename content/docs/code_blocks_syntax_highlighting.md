+++
title = "Code Blocks and Syntax Highlighting"
description = "Configure and use code blocks, line numbers, and highlighted lines in Zolbare."
date = 2026-10-13
authors = ["Vince"]

[taxonomies]
tags = ["code", "syntax-highlighting", "developer"]
series = ["Making the Most of Zolbare"]

[extra]
order = 4

[[extra.widgets]]
title = "Syntax Highlighting"
items = [
{ name = "Zola Documentation", url = "https://www.getzola.org/documentation/content/syntax-highlighting/", out = true },
{ name = "Catppuccin Latte", url = "https://github.com/shikijs/textmate-grammars-themes/blob/main/packages/tm-themes/themes/catppuccin-latte.json", out = true },
{ name = "GitHub Dark", url = "https://github.com/shikijs/textmate-grammars-themes/blob/main/packages/tm-themes/themes/github-dark.json", out = true },
{ name = "Giallo README", url = "https://github.com/getzola/giallo#built-in", out = true },
{ name = "Theme Preview", url = "https://textmate-grammars-themes.netlify.app/", out = true },
{ name = "Theme Repository", url = "https://github.com/vincentdesiree/zolbare", out = true }
]
+++
Good code highlighting makes technical articles easier to read. Zolbare uses Zola's built-in syntax highlighting, powered by Giallo, with support for multiple languages, line numbers, and highlighted lines.

## Configure the colors

Syntax highlighting is configured in your site's `zola.toml`:

```toml
[markdown.highlighting]
light_theme = "catppuccin-latte"
dark_theme = "github-dark"
error_on_missing_language = false
```

Zolbare uses **Catppuccin Latte** for light mode and **GitHub Dark** for dark mode by default.

You can change either theme to another supported name. Check the links in the sidebar to browse available themes and preview their colors.

Setting `error_on_missing_language = false` means an unkown language identifier won't cause a build error.

## Additional languages and themes

Zola uses Giallo, which provides a built-in collection of languages and themes. You can browse the available options in the Giallo README or preview themes using the links in the sidebar.

If a language or theme isn't included, you can add custom TextMate grammar or theme files in JSON format.

For example, place a grammar file at `extra/my_language.json` and register it in `zola.toml`:

```toml
[markdown.highlighting]
extra_grammars = ["extra/my_language.json"]
```

For a custom theme, use `extra_themes`:

```toml
[markdown.highlighting]
extra_themes = ["extra/my_theme.json"]
```

The paths are relative to the directory containing `zola.toml`. To use a custom grammar, set the code fence language identifier to the grammar's top-level `name` field. For a custom theme, set `light_theme` or `dark_theme` to the theme file's top-level `name` field.


## Use different languages

Add a language identifier after the opening backticks. Zola will use it to select the appropriate syntax highlighting rules.

**Rust**

```rust
fn greet(name: &str) -> String {
    format!("Hello, {name}!")
}
```

**JavaScript**

```javascript
const greet = (name) => `Hello, ${name}!`;

console.log(greet("Zolbare"));
```

**Python**

```python
def greet(name: str) -> str:
    return f"Hello, {name}!"

print(greet("Zolbare"))
```

**TOML**

```toml
title = "My Site"

[markdown.highlighting]
light_theme = "catppuccin-latte"
dark_theme = "github-dark"
```

**HTML**

```html
<article>
    <h1>Hello, Zolbare!</h1>
    <p>A simple example.</p>
</article>
```

**CSS**

```css
.article-content {
    max-width: 75ch;
    line-height: 1.6;
}
```

**Shell**

```sh
zola serve
zola build
```

You can also use languages such as SQL, JSON, YAML, PHP, Go, and many others. See the Zola documentation for the full list of supported languages.

**Plain text**
```
You can also use this without specifying any language
```

## Add line numbers

Use `linenos` in the code fence to display line numbers:

````markdown
```rust,linenos
fn main() {
    println!("Hello, Zolbare!");
}
```
````

```rust,linenos
fn main() {
    println!("Hello, Zolbare!");
}
```

## Start numbering from a different line

Use `linenostart` when showing a snippet taken from a larger file:

````markdown
```rust,linenos,linenostart=10
fn main() {
    println!("Hello, Zolbare!");
}
```
````

```rust,linenos,linenostart=10
fn main() {
    println!("Hello, Zolbare!");
}
```

The first displayed line will be numbered `10` instead of `1`.

## Highlight specific lines

Use `hl_lines` to emphasize important lines. You can specify individual lines and ranges:

````markdown
```rust,linenos,linenostart=10,hl_lines=2-3 5
fn main() {
    let name = "Zolbare";
    let message = format!("Hello, {name}!");
    println!("{message}");
}
```
````

```rust,linenos,linenostart=10,hl_lines=2-3 5
fn main() {
    let name = "Zolbare";
    let message = format!("Hello, {name}!");
    println!("{message}");
}
```

Here, lines 2–3 and 5 are highlighted.

**Note:** `hl_lines` counts lines from the beginning of the code block, starting at `1`. It is independent of `linenostart`, which only changes the displayed line numbers.

## Hide lines

Use `hide_lines` to hide specific lines from the rendered code block. You can specify individual lines or ranges, using line numbers starting at `1`.

````markdown
```rust,linenos,hide_lines=1-2
fn main() {
    let name = "Zolbare";
    let message = format!("Hello, {name}!");
    println!("{message}");
}
```
````

With the first two lines hidden, the rendered block displays:

```rust,linenos,hide_lines=1-2
fn main() {
    let name = "Zolbare";
    let message = format!("Hello, {name}!");
    println!("{message}");
}
```

You can also hide individual lines or multiple ranges, for example with `hide_lines=1 3-4`.


## Handle long lines

Some code doesn't fit within the available width. Zolbare allows code blocks to scroll horizontally when needed, rather than forcing long lines to wrap awkwardly.

This is useful for commands, URLs, and code where line breaks would affect readability or meaning.

## Recap: code block features

Zolbare supports the following code block features through Zola's syntax highlighting:

* **Syntax highlighting:** specify a language to apply the corresponding highlighting rules, or omit it for plain text.
* **Light and dark themes:** configure separate highlighting themes in `zola.toml`.
* **Line numbers:** enable numbering with `linenos`.
* **Custom starting numbers:** use `linenostart` to number a snippet from its original position in a larger file.
* **Highlighted lines:** use `hl_lines` to emphasize specific lines or ranges.
* **Hidden lines:** use `hide_lines` to omit selected lines from the rendered block.
* **Horizontal scrolling:** long code lines can scroll horizontally instead of forcing the code block to wrap.
* **Additional languages and themes:** extend the built-in collection with custom grammars and themes.
