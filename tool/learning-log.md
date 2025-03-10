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
 * How do I learn.
###
*

<!--
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
