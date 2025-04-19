# Entry 5
##### 4/1/25

### Jekyll Part 2
After learning about the basics of Jekyll, I learned more advanced things such as `liquid` and `font-matter-defaults`.
### What I've learned:
* `{% assign variable="variable-name" %}`
 * Makes a variable and set its value to "variable-name".
* `| filler`
 * Goes right before `%}` and changes the string.
   * Strings are basically, what the user see when they load the website.
* `{{ variable }}`
 * A piece of liquid code that shows a variable as a string.
* `{% if variable="text" %}`
 * If the **statement is true**, run:
  * Ends with `{% endif %}`.
* `{% if variable contains "text" %}`
 * If the variable contains this **text**, run:
* `{% elsif %}`
 * Allows a second condition to be true to make a different string.
* `{% unless %}`
 * Opposite of `if`.
* `{% for names in author.names %}`
 * `For loop`, allows the code to run multiple times.
``` yaml
defaults:
  -
    scope:
      path: "" # an empty string here means all files in the project
    values:
      type: "posts"
      layout: "post"
      author: "William"
```
  * Sets the _layout_ to be "post" on all posts (In `_posts`) and the author variable to be "William".
 * `{% hightlight ruby %}`
  * Jekyll's own code for **syntax highlighting** and showing code on a website.
* `gem "github-pages", "~> 232", group: :jekyll_plugins`
 * Also add a `#` in front of `gem "jekyll", "~> 4.3.4"`.
  * Jekyll has a different way of using `github pages`, you must change the gem to `github-pages`.
``` yaml
---
title:  "Jekyll Summary"
date:   2025-02-24 14:09:28 -0500
categories: jekyll-update
permalink: /welcome-to-jekyll/
layout: post.html
---
```
 * **Font matter** for a page.
 * Allows you to change the **settings** for a page, also allows for the creation of _variables_.
* `_includes`
 * A special directory that allows you to "include" pieces of code in your text.
 * `{% include bootstrap-head-required.html %}`
  * Places the text in `bootstrap-head-required.html` in the area where it's placed.
* Changing `Gemfile.lock`.
 * Delete `Gemfile.lock` and do `bundle install` to get an updated version.
* `href="{{ site.baseurl }}{% link _posts/2025-03-05-html-file.html %}"`
 * Required to use this syntax for links to use `github pages`.
### How I learned:
When learning more about Jekyll **beyond** the basics, I mainly learned about `liquid` code from [this website](https://shopify.github.io/liquid/basics/introduction/). However, I also learned about Jekyll's own `liquid` tags from [the official Jekyll site](https://jekyllrb.com/).
Afterwards, I mainly used [this site](https://talk.jekyllrb.com/) whenever I encountered an error.

Here's how it went:
I first started off by going to [a site that teaches the basics of `liquid`](https://shopify.github.io/liquid/basics/introduction/) and going through the proper formatting with how to make and use variables.

For example,
``` 



[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)
