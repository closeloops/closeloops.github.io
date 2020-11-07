C.LOOP Website [![Build Status](https://travis-ci.org/mono/website.svg)](https://travis-ci.org/mono/website)
==================================================================================================================

This repository contains the files used for generating the [C.LOOP website](http://closeloop.github.io).

The site uses [Jekyll](http://jekyllrb.com), a static site generator. GitHub Pages, where the site is hosted, natively supports Jekyll so every time someone pushes to this repository, the website will be built and updated. For hosting it yourself, see [Setting up a local copy of the website](#setting-up-a-local-copy-of-the-website).

Contributing to the website
---------------------------

**Note:** Major issues or feature requests should be filed on the [issue tracker](https://github.com/mono/website/issues) first, so we can discuss the implications.

Setting up a local copy of the website
--------------------------------------

For larger changes, using the web-based editor on GitHub is not really convenient. A better way is to setup a local copy of the website where you can experiment.

### Dependencies

 - [Ruby](https://www.ruby-lang.org/) - Jekyll is written in Ruby
 - [Bundler](http://bundler.io/) - a package manager for Ruby. Install it by running `gem install bundler`

After you've forked and cloned the repository, run the following commands:
 1. `bundle install` - downloads the required libraries
 2. `bundle exec jekyll serve` - builds the website and runs a local webserver on port 4000

**Note:** you can add the `--watch` option when running `jekyll serve` to let Jekyll watch for file changes, which means the site will be rebuilt when a file is modified.

**Note 2:** on case-insensitive file systems like on Windows and macOS you'll run into redirect loops for some URLs. The workaround is to disable redirects locally by removing the `gems: jekyll-redirect-from` entry from `_config.yml`.

Repository structure
--------------------

 - `_includes` - *special folder* contains snippets that can be included via `{% include file.html %}` in other pages
 - `_layouts` - *special folder* contains the layouts that are shared between pages. Layouts can be inherited, the root layout is `base.html`.
 - `_posts` - *special folder*, contains the source pages for the blog section, see [Writing a blog post](#writing-a-blog-post)
 - `_site` - the output of the generated site is stored here by default, this folder only exists after Jekyll built the site
 - `archived` - content that is no longer relevant but kept to keep external links working
 - `community` - contains the source pages for the `/community` website section
 - `css` - contains the main stylesheet
 - `docs` - contains the source pages for the `/docs` website section
 - `download` - contains the source pages for the `/download` website section
 - `files` - stores binary files used in pages
 - `images` - stores the images used in pages
 - `news` - lists the blog pages from the `_posts` directory

Writing a blog post
-------------------

Blogging is very easy with Jekyll. Browse to `_posts` directory, copy the Markdown file `_TEMPLATE.md` and rename that file following the file name convention: `YEAR-MONTH-DAY-title.md`. Then open the file you renamed and follow the steps there to complete writing a blog post.

Make sure to not include special characters in the file name. The blog entry's publishing date is automatically extracted from the file name.
