# beerriot-jekyll-theme

If you're not deploying one of the beerriot.com sites, you probably
don't want this theme. Or at least, not without significant
changes. It's a simple design based on responsive Pure.CSS grids, but
the default layout also includes header metadata, menu links, and a
logo specific to *.beerriot.com. If the GitHub Pages renderer didn't
need this repo to be public, I'd probably keep it private just to
avoid confusion.

### Information for future-Bryan to remember:

For developing locally, the easiest way to get this theme working was:

1. Checkout this repo at `/Users/bryan/projects/beerriot-jekyll-theme`
2. Add to site `Gemfile`: `gem "beerriot-jekyll-theme", path: "/Users/bryan/projects/beerriot-jekyll-theme"`
3. Add to site `_config.yaml`: `theme: beerriot-jekyll-theme`

Maybe a `bundle install` was needed between steps 1 and 2, but probably not?

For deploying on GitHub Pages, I think all that will be needed is to add `remote_theme: beerriot/beerriot-jekyll-theme` to the site's `_config.yaml`.

### Further tips:

Defaults make front-matter easier. In the site's `_config.yaml`, add:

```
defaults:
  -
    scope:
      path: "" # an empty string here means all files in the project
    values:
      layout: "default"
  -
    scope:
      path: ""
      type: "posts"
    values:
      layout: "post"
```

Lots of things in the default layout are configurable:

 * `site.subtitle`: what, if anything, to put after "BeerRiot", and
   before ": <Title>". ex: "Blog" for "BeerRiot Blog: <Title>"

 * `site.email_suffix`: what to add between `bryan+` and
   `@beerriot.com` in the email link, to attempt to get an idea of
   which link was used

 * `_includes/site_head_links.html`: anything that should go in the
   `<head>` of the site's pages

 * `_includes/site_social_links.html`: any icon links to add below the
   logo in the top left

 * `_includes/site_menu_links`: anything to add to the left-side menu
   after the domain links
