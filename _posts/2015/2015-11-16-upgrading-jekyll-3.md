---
title: Upgrading to Jekyll 3.0
date: 2015-11-16
category: Development
---

Jekyll 3.0 was released in late October, and since I was building my personal site using this platform I decided to upgrade from version 2.5.2.

I upgraded using `sudo gem update jekyll`. After the update, I did a `jekyll serve`, and Jekyll did not build my site. I will show you some of the issues I encountered and how I fixed them.

- The first warning Jekyll showed me in the build process was this:
```
Deprecation: You appear to have pagination turned on, but you haven't included the `jekyll-paginate` gem. Ensure you have `gems: [jekyll-paginate]` in your configuration file.
```

Jekyll 3.0 requires the jekyll-paginate dependency installed for the pagination feature to work properly. To install it, I wrote `sudo gem install jekyll-paginate` in my terminal. This setup requires this gem to be specified in the `_config.yml` file:

```
gems:[jekyll-paginate]
```

- If you want to embed GitHub gists in a post, Jekyll 3 now requires for this gem to be specified in the `_config.yml` file as well. I had to install the gem: `gem install jekyll-gist`, and added it to the configuration file:

```
gems:[jekyll-paginate, jekyll-gist]
```

- It's important to note, that the default syntax highlighter is Rouge, instead of Pygments. I didn't have Pygments specified as the highlighter, but if it is, this line should be removed from the configuration file:

`highlighter: pygments`

Just to be safe, I added these lines to the Kramdown configuration:

```
kramdown:
    input: GFM
    syntax_highlighter: rouge
```  
