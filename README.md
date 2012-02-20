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
* **feed_dir** - *optional* - *(default: feed)* - Directory in the output
    folder where the generated feeds will be placed.

When you run Jekyll feeds will be placed into your set `feed_dir` or the
directory `feed` if you haven't specified it in your configuration.

As example, lets say you have two categories, **Art** for posts related to
artwork and **Technology** for techy blog posts.  Your feeds will be placed in
your site's output folder and should look something similar to this:

    |- _site/
    | |- feed/
    | | |- Art/
    | | | |- atom.xml
    | | |- Technology/
    | | | |- atom.xml
    | |- atom.xml

The `feed/atom.xml` file will contain posts from all categories.

### Liquid Tag

In your site you may want to link to the feed associated with the category of
your page.  A liquid tag is provided to do just this; just include `{%
page_feed_url %}` in your page.  The url to the feed will match the category
associated with your page.

If you want to allow automatic discovery of your feeds, you can include this in
your header.

    <link rel="alternate" type="application/atom+xml" title="Atom feed" href="{% page_feed_url %}" />

If your page has a category in it's url, such as `Art`, it will point to the
feed for that category.  If we can't match a category in the url, the feed
containing all posts is given.

Contributing
------------

Feel free to fork this project, send me pull requests, and issues through [the
project's github page][project-page].

[project-page]: https://github.com/MrWerewolf/jekyll-category-feeds