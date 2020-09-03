---
title: "Page 1"
date: 2020-09-03T22:09:04+01:00
draft: true
tags: ["tag1", "tag2"]
categories: ["cat2"]
moods: ["happy", "mysterious"]
---

To create a new site, run `hugo new site mysitename` in the terminal.

To create a new page, run `hugo new page.md` in the terminal. To create a new page within a diretory, run `hugo new dir/page.md`.

To run the site locally, run `hugo server` in the terminal. To build the site including draft pages, run `hugo server -D`.

Edit archetypes/default.md to change the default front matter generated. To set default front matter for specific diretories, create files in archetypes with the name of the directory.

To add html snippets (short code), type {{< youtube U-C0I-Ks14M >}}

To create a custom taxonomy, `moods`, in your config.toml create a new array listing all used taxononomies (including the default tags and categories). Put singular on the left and plural on the right:

``` yaml
[taxonomies]
  tag = "tag"
  category = "categories"
  mood = "moods"
```
