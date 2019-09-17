---
layout: single
excerpt: "Jekyll Setup"
sitemap: false
permalink: /pages/jekyll/
---
## Jekyll Development Setup ##
Brief instructions describing the Jekyll 'ioos_jekyll_theme' theme setup for local development.  Following these instructions,
including the Jekyll dependency installation will provide you a full development environment and the template code used
to run this site.

### Requirements/References: ###
- Ruby: [https://www.ruby-lang.org/en/](https://www.ruby-lang.org/en/), Windows users:
  [Ruby Installer for Windows](http://rubyinstaller.org/downloads/)
- Jekyll: [https://jekyllrb.com/](https://jekyllrb.com/) (for reference, no need to download as it's available as a Ruby gem)
- Minimal Mistakes Jekyll theme: [https://mmistakes.github.io/minimal-mistakes/](https://mmistakes.github.io/minimal-mistakes/)

*\*Minimal Mistakes theme was the base theme used for the site*


### Installation: ###
- Install Ruby for your environment (via package manager(unix) or installer (win)).  See instructions on the Ruby site.

- Install Jekyll in your Ruby environment:

```
gem install jekyll
```

- The Minimal Mistakes theme (basis for the ioos_jekyll_theme) recommends installing Bundler for dependency
management to run Jekyll more easily.  See the [install docs](https://mmistakes.github.io/minimal-mistakes/docs/installation/)
for more info.

```
gem install bundler
```

- Clone the ioos_jekyll_theme GitHub repo ('gh-pages' branch) to get this example code.  This will include a
git submodule reference to the 'master' branch which includes the theme itself.  

```
cd /my/sourcecode/dir
git clone --recursive -b gh-pages https://github.com/ioos/ioos_jekyll_theme.git
cd ioos_jekyll_theme
```

- Install dependencies via Bundler:

```
bundle install
```


- From here, you should be able to run Jekyll to preview the site using the commands below.  Different options listed in the three
command examples below highlight the development settings available in Jekyll for verbose logging and watching for code
changes as you edit markdown files and automatically recompiling the HTML for preview.  

```
bundle exec jekyll serve --config _config.yml,_config_dev.yml
bundle exec jekyll serve --config _config.yml,_config_dev.yml --watch --verbose
bundle exec jekyll serve --config _config.yml,_config_dev.yml --watch --verbose --incremental
```

Note: the - -config flag allows local overrides of the site.url for development/testing
in the \_config_dev.yml file, while the production version when pushed to GitHub will use the settings in
the standard Jekyll \_config.yml file only.

Out of the box, this will publish a local Jekyll service listening on port 4000, with the site available at this URL:

[http://localhost:4000/ioos_jekyll_theme/](http://localhost:4000/ioos_jekyll_theme/)

The path the site is deployed to should be modified to match your repository name by changing the 'baseurl' setting
 in the \_config.yml (primary Jekyll config/GitHub Pages deployment settings file) and the \_config_dev.yml
(local development settings override) files.
