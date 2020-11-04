+++
author = "Sonia Mitchell"
title = "How to build a website in Hugo"
date = "2020-11-04"
description = "How to build a website in Hugo"
tags = [
    "hugo",
    "website",
    "custom_domain",
]
categories = [
    "website",
    "coding",
]
series = ["Website Guide"]
+++

To create a new site, run `hugo new site mysitename` in the terminal.

Find a nice [theme](https://themes.gohugo.io) and go to the GitHub page. Download the theme as a *.zip file and unzip it into the themes directory. Copy and replace config.toml with themes/mytheme/exampleSite/config.toml and make sure the name matches the name of the theme you just downloaded (you might need to delete `-master`). Replace the contents of the content directory with the contents of themes/mytheme/exampleSite/content.

To run the site locally, run `hugo server` in the terminal.

Push files to a hugo_source_files GitHub repository.

Generate a yaml file and save it in `.github/build.yaml`:

``` yaml
name: Build and Deploy

on:
  push:
    branches:
      - master

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
    - name: Checkout master
      uses: actions/checkout@v1
      with:
        submodules: true

    - name: Hugo Deploy GitHub Pages
      uses: benmatselby/hugo-deploy-gh-pages@master
      env:
        HUGO_VERSION: 0.68.3
        TARGET_REPO: soniamitchell/soniamitchell.github.io
        TOKEN: ${{ secrets.HUGO_TOKEN }}
        CNAME: sonia-mitchell.com
```

where TARGET_REPO points at your username.github.io repository and HUGO_TOKEN is a PAT.

Go to settings and put your custom domain in custom domain. This will create a CNAME file. Copy the contents of this file into the CNAME field in the build.yaml.
