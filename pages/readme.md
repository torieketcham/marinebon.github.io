---
layout: single
excerpt: "IOOS Jekyll Theme Getting Started"
sitemap: false
permalink: /pages/readme/
---

tylar was here

## IOOS Jekyll Theme Getting Started ##
This repo holds the common Jekyll theme code for IOOS GitHub.io documentation sites.  The IOOS theme is based on IOOS'
fork of the ['Minimal Mistakes'](https://github.com/mmistakes/minimal-mistakes)
Jekyll theme originally developed for the [IOOS Catalog documentation site](https://ioos.github.io/catalog/).  

This single IOOS theme was developed to streamline and simplify management of the IOOS documentation sites hosted on
GitHub Pages (aka GitHub.io).  When a new IOOS documentation site is built following the instructions described here,
it will provide a consistent look and feel across all of IOOS' project documentation sites, and will simplify the process
to update the template across each site if needed.  

This is accomplished by using the git submodule concept, which
allows each individual documentation site to reference this template for the Jekyll boilerplate code.  Updating each
downstream documentation site can be accomplished by a `git submodule update` command, rather than separately modifying
the Jekyll boilerplate code to match in each.  

## Getting the IOOS Jekyll Theme ##
Deploying this template for your own IOOS-branded GitHub Pages documentation site can be done in a couple different ways.

The main difference in the approach you take is whether you want to run the Jekyll development environment locally (for
  more rapid iterative markdown/content update), or if you prefer to use GitHub Pages' own Jekyll framework to render your
  updates (GitHub Pages internally uses Jekyll to render HTML from markdown).  This means you can copy the example code
  in this repository into your own repository 'gh-pages' branch, make a few config file modifications, and push to GitHub
  directly to see a rendered site matching exactly this site without any special software on your workstation (other than
  perhaps a GitHub client for pushing updates to GitHub).  

### 1. Local Jekyll Development: ###
Running Jekyll locally will allow for faster site development, but you must be able to install Ruby on your workstation.

If you are able to run the Ruby/Jekyll environment locally, refer to the [Jekyll Development Environment Set Up](https://ioos.github.io/mbon_jekyll_theme/pages/jekyll/)
page for the steps required for this approach.

### 2.  GitHub Pages-based Development: ###
If you can't run Ruby/Jekyll on your workstation, you can still make a GitHub Pages documentation site based on this
template.  The process to do this is to download the code from the ['gh-pages'](https://github.com/ioos/mbon_jekyll_theme/tree/gh-pages)
branch of this repository, adapt for your site needs, and publish to a 'gh-pages' branch of your own repository.  Instructions to do this:

```
cd /my/sourcecode/dir
git clone --recursive -b gh-pages https://github.com/ioos/mbon_jekyll_theme.git
cd mbon_jekyll_theme
```
Next, you will need to copy the files downloaded to the 'mbon_jekyll_theme' directory to your target repository.
Assuming you have an existing repository, the easiest way to do this is to create a new 'gh-pages' branch, and then remove
all git-tracked files and replace by the template code.  Roughly, this looks like (use with caution):

```
cd /my/target/repository
git checkout -b gh-pages master
git rm -r *
git rm .*
```
Then copy from the mbon_jekyll_theme repository and add all the file to git for tracking ```git add *```.
Once you have the code in hand, instructions below describe relevant files to modify to adapt the template to your needs.\

When you've made changes and you would like to see how they look on your GitHub Pages site, simply commit and push them
up to your GitHub repo:

```
git commit -am "Initial GitHub Pages site built using 'mbon_jekyll_theme'"
git push origin gh-pages
```

## Modifying Theme Content For Your Site ##
The important files and directories to modify the template are the following:

|**Name**|**Description**|
|--------|------------|
|\_config.yml and \_config_dev.yml| Main Jekyll configuration files.  Modify settings in these to change anything related to the theme|
|/\_data/navigation.yml| Configuration file for main header categories and side navigation bar(s) to use in your site|
|/\_pages/| Directory to place any standard 'page' markdown content to publish|
|index.html| This markdown/HTML hybrid file contains the content for the splash page for the site|

- \_config.yml and \_config_dev.yml:  Important settings to update in these files are primarily in the top of the file,
and include settings like: 'title', 'name', 'description', 'baseurl', among others.  More documentation can be found in
the Minimal Mistakes documentation (see below).

- \_data/navigation.yml: This file contains the settings for both the page header categories and destinations, as well
as the side bar navigation menu(s).  You can configure multiple side bars if needed (for different content types).
Associations between the content types (ie Jekyll 'colllections') and the side bar to display for each can be set in
the \_config.yml file, or in the front matter of the markdown page (for more granularity).  Further description of how
this works is beyond the scope here, refer to the Jekyll and Minimal Mistakes documentation for more info.


## References ##  
Jekyll [Documentation](https://jekyllrb.com/docs/home/).

Documentation for working with the Minimal Mistakes template is can be found here:
[https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/).

### GitHub Pages and Jekyll ###
Information on the way GitHub uses Jekyll in 'GitHub Pages' sites can be found here:
[https://help.github.com/articles/about-github-pages-and-jekyll/](https://help.github.com/articles/about-github-pages-and-jekyll/)

In particular, to push documentation for a 'Project' page (which most repos will fall under), use a
specially-named branch 'gh-pages' to push content to.  More information on this requirement can be
found here: [https://help.github.com/articles/user-organization-and-project-pages/](https://help.github.com/articles/user-organization-and-project-pages/).
