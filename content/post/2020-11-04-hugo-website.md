---
title: Build a website in Hugo
subtitle: A how to guide
date: 2020-11-04
tags: ["hugo", "website", "custom domain", "coding"]
---

## Step 1 - Creating your website locally

We're going to do this on a Mac. Things might be a bit different if you're using Windows, so be aware of that.

First you need to install hugo. You can do this in the terminal:

``` bash
brew install hugo
```

Now decide where you want your website to be created. I like to keep all my work in a Desktop folder called git. Go to this directory.

``` bash
cd ~/Desktop/git/
```

To create a new website, run:

``` bash
hugo new site my_site_name
```

This will create a new directory called `my_site_name`, which should look like this:

```
my_site_name/
    archetypes/
        default.md
    content/
    data/
    layout/
    static/
    themes/
    config.toml
```

The next thing to do is pick a theme. You want your website to look good! So go to [https://themes.gohugo.io](https://themes.gohugo.io), find a nice theme, and go to its homepage. I've chosen the Erblog theme. Hopefully, you're now in a [GitHub repository](https://github.com/ertuil/erblog). Click on the green "Code" button and download the repository as a ZIP file. You should now have a folder in Downloads called `erblog-master`. Rename it as `erblog` and put it in `themes/`.

Now we need to do a bit of copy and pasting. Copy the contents of `erblog/exampleSite/config.toml` and paste it into `config.toml`. Likewise, copy the files in `ghostwriter/exampleSite/content/` into `content/`. You're now ready to build your site!

To build it locally, go into your website directory

``` bash
cd my_site_name
```

and run

``` bash
hugo server
```

You'll get a message saying your website is available at `localhost:1313/`. Copy this link in your browser to see what your website looks like. It looks great!

Note that `content/` holds the contents of your website. You might want to tinker about with these, as well as your `config.toml` file to customise your website. Any saved changes you make should automatically rebuild the site in your browser. Unless something goes wrong... or you press Ctrl+C to break the connection.  

## Step 2 - Creating your website remotely

Now that your website is full of great content, we should put it online. You can do that for free if you have a GitHub account.

So, go to GitHub - hopefully you already have an account – and make a new repository. I've named mine `hugo_source_files`. Initialise `my_site_name/` as a local repository and push its contents to your new hugo_source_files repository on GitHub. Now your files are backed up on GitHub, but your website isn't online yet. We want our website to build itself automatically. So the next step is to ask GitHub to do this for us.

First, you need to make a secret. So in GitHub, go to "Settings", then "Developer settings", then "Personal access tokens", and "Generate new token". Type `HUGO_TOKEN` in the Note section and check the box next to "repo" in "Select scopes". Scroll down and click "Generate token". This will generate an alphanumeric string, 40 characters long (this is your PAT). Copy it or click on the little clipboard icon. Now go back to your `hugo_source_files` repository. Go to "Settings", then "Secrets", and "New secret". Make the name `HUGO_TOKEN`, paste your PAT into the value box, and click "Add secret".

Next, create a second repository on GitHub called `github_user_name.github.io`, replacing github_user_name with whatever your GitHub username is.

And finally, go back to `my_site_name/` and create a new directory called `.github/`, in here create a new file called `build.yaml` containing:

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
```

There are two things to notice here. `TARGET_REPO` should point to `github_user_name/github_user_name.github.io` and `TOKEN` references your `HUGO_TOKEN` secret.

Now push this file to your `hugo_source_files` repository.

## Step 3 - Linking to a private domain

Go to settings and put your custom domain in custom domain. This will create a `CNAME` file. Now add an extra field to the end of your `build.yaml` file like this:

``` yaml
    - name: Hugo Deploy GitHub Pages
      uses: benmatselby/hugo-deploy-gh-pages@master
      env:
        HUGO_VERSION: 0.68.3
        TARGET_REPO: soniamitchell/soniamitchell.github.io
        TOKEN: ${{ secrets.HUGO_TOKEN }}
        CNAME: sonia-mitchell.com
```

Copy the contents of this file into the `CNAME` field in `build.yaml` and push these changes to GitHub. Assuming you have everything set up correctly from your domain provider, your website should be redirected.
