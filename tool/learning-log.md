# Tool Learning Log

## Tool: **Jekyll**

---

### 3/3/25:
* Learning how to make layouts.
 * https://www.youtube.com/watch?v=bDQsGdCWv4I
* Write layouts in .html
* {{ content }} variable that is all the content in your post.
* You can add font matter to a layout to have multiple layouts in a post.
### 3/4/25:
* https://jekyllrb.com/docs/includes/
 * _includes is a directory you can make in /root that allows you to use:
  * {% include footer.html %} Includes content from a file inside of _includes
  * {% include_relative somedir/footer.html %} Includes content from a file relative to the current file.
   * Does not work with ../
 * https://github.com/brianmueller/cssi-curriculum is not a tutorial for Jekyll (Spent half the period going through this)
* Layouts are especially useful many files need the same exact html. (nav bar, footers, headers, etc)
* Next steps: Making a separate nav bar at the side and (maybe) adding SEP notes into Jekyll.
 * Should also learn how to make the local repository into remote.
### 3/5/25
Uses `<nav>`
* https://www.youtube.com/watch?v=6h8-uPadFug
* Layout nav bar:
``` HTML
<nav>
<ul>
<li> <a href=”/about/” > About </a>
</ul>
 </nav>
 ```
Inside of a post- file: permalink: /about/

`nav ul` { Inside of the ul inside the nav will have:

}
`nav ul li`{ Inside of the li inside of the ul inside of the ul will have:
}

``` CSS
nav ul li a:hover {    When you hover over <a> inside of li...
text-decoration: underline;
color:cyan;
}
```
home is `/` (for permalinks)

* `{% include head-bootstrap.html %}`
 * Inside of your _includes folder, it includes everything inside of head-bootstrap.html
  * Liquid tag
* You can use bootstrap with Jekyll
### 3/10/25
* JEKYLL DOESN'T WORK!!!
#### 3/10/25 (Afternoon)
* I managed to fix the error that kept popping up when I used Jekyll commands.
 * I worked on debugging my dropdowns and further testing in layouts/includes folder.
* What I found was that files in _includes are written in the exact spot where you put them in. For example, if you put `{% include bootstrap-required.html %}` in the `<head>`, it will only appear there. Even if you had a separate section in the `includes` file, `<body>`, it wouldn't work, everything would be registered as inside of `<head>`. This way, you need both a `bootstrap-head-required.html` and a `bootstrap-body-required.html`.
* However, curiously, if you have a layout, you only need one of them to have the correct `includes` file, the rest do not need them. (If you properly link layouts together)

#### 3/17/25
* Categories are for structuring blog posts.
* There doesn't seem to be anything for making presets for categories.
* Categories probably just bring all the posts under a certain category together.
Example: food > informative > personal-information > something-else.
* Summary: Just give the same category to each post that are under a certain label; example: informational; css; html; javascript, etc.
* Inside of `font-matter`.
#### 3/18/25
* THEMES
 * Themes are basically templates made by the jekyll community.
* If you want to use a theme, you can just fork a theme's repository.
 * I forked the chirpy theme and changed a few lines of text.
* Pretty sure you can also use `config.yml` to install a theme.
* Also used the `Lanyon` theme.

<!--
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
