+++
title = "Installing and Configuring Zolbare"
description = "Install Zolbare in your Zola project and keep control of when theme updates reach your site."
date = 2026-10-02
authors = ["Vince"]

[ taxonomies ]
tags = ["zola", "installation", "configuration"]
series = ["Getting Started with Zolbare"]

[extra]
order = 2

[[extra.widgets]]
title = "Installation Resources"
items = [
  { name = "Zola Installation", url = "https://www.getzola.org/documentation/getting-started/installation/", out = true },
  { name = "Configuration", url = "https://www.getzola.org/documentation/getting-started/configuration/", out = true },
  { name = "Theme Repository", url = "https://github.com/vincentdesiree/zolbare", out = true }
]
+++
Zolbare works with [Zola](https://www.getzola.org/), a fast static site generator. If you already have a Zola site, you're ready to go.

## 1. Get the theme

Create the theme directory if it doesn't exist yet and clone the Zolbare repository in it:

```sh
mkdir -p themes
git clone https://github.com/vincentdesiree/zolbare.git themes/zolbare/
rm -rf themes/zolbare/.git
```

This copies the theme into your project without keeping it as a separate Git repository. Your site's Git repository can then track the theme files directly.

## 2. Enable Zolbare

Open `zola.toml` and set the theme at the top level:

```toml
theme = "zolbare"
```

If your configuration already contains other settings, keep them. Just make sure `theme` isn't placed inside a section such as `[extra]` or `[markdown]`.

## 3. Run your site

Start the local development server:

```sh
zola serve
```

Open the local URL shown in your terminal. To generate the production site, run:

```sh
zola build
```

## 4. Keep updates under control

Because the theme files live directly in your project, updates are deliberate: review the changes, copy them into your site, and test before deploying.

This approach avoids automatically pulling theme changes into a deployment. It also means you'll need to manage updates yourself.

That's it. Zolbare is installed and ready for your content.
