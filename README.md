Jekyll Category Feeds
=====================

This jekyll plugin generates [Atom](http://www.atomenabled.org/) feeds for
your site.  One feed will be generated that includes all posts from your site,
while the rest of the feeds will be broken down by category.

Installation
------------

Place the `category_feeds.rb` file into the `_plugins` directory of your Jekyll
site.  If the directory does not exist, create it.

Dependencies
------------

This plugin requires Atom-Tools to be installed.  To install this, just run the following:

    gem install atom-tools

Usage
-----

For feeds to be generated correctly, you'll need some options set in your site's
`_config.yml` file.

* **url** - *required* - Full public url of your site without a trailing slash.
* **name** - *required* - The name/title of your site.
* **tagline** - *optional* - Site tagline/subtitle.
* **author** - *optional* - The site author.
* **email** - *optional* - The site author's email.
* **feed_dir** - *optional* - *(default: feeds)* - Directory in the output
    folder where the generated feeds will be placed.

When you run Jekyll feeds will be placed into your set `feed_dir` or the
directory `feeds` if you haven't specified it in your configuration.

As example, lets say you have two categories, **Art** for posts related to
artwork and **Technology** for techy blog posts.  Your feeds will be placed in
your site's output folder and should look something similar to this:

    |- _site/
    | |- feeds/
    | | |- Art/
    | | | |- atom.xml
    | | |- Technology/
    | | | |- atom.xml
    | |- atom.xml

The `feeds/atom.xml` will contain posts from all categories.

Contributing
------------

Feel free to fork this project, send me pull requests, and issues through [the
project's github page][project-page].

[project-page]: https://github.com/MrWerewolf/jekyll-category-feeds