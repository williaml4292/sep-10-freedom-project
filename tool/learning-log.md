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
* Layouts are especially useful as many files need the same exact html. (nav bar, footers, headers, etc)
* Next steps: Making a separate nav bar at the side and (maybe) adding SEP notes into Jekyll.
 * Should also learn how to make the local repository remote.
### 3/5/25
Uses `<nav>`
* https://www.youtube.com/watch?v=6h8-uPadFug
* Layout navbar:
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
* Summary: Just give the same category to each post that is under a certain label; example: informational; css; html; javascript, etc.
* Inside of `font-matter`.
#### 3/18/25
* THEMES
 * Themes are basically templates made by the jekyll community.
* If you want to use a theme, you can just fork a theme's repository and use `bundle install`.
 * I forked the chirpy theme and changed a few lines of text.
* Pretty sure you can also use `config.yml` to install a theme.
* Also tried using the `Lanyon` theme; but it didn't work.
 * It uses a variation of jekyll, specifically a bootstrap one.
  * Doesn't have a gemfile, so you can't just do `bundle install`.
#### 3/24/25
* LIQUID
 * Jekyll uses liquid for templating, so I'm going to try to learn how to use liquid. (basic understanding)
* [Introduction](https://shopify.github.io/liquid/basics/introduction/)
* [Tutorial](https://liquidjs.com/tutorials/intro-to-liquid.html)
* Outputs: Output **variables** that can be changed via fillers, into html.
* Liquid tags are wrapped in `{{} OBJECTS-&-Variables }}` (or) `{% tags %}`
 * Objects are what is displayed on the page.
 * Tags are logic and control flow in templates (does not appear on webpage)
  * Assign variables and make `if` `else` statements.
* `{{ username | append: ", welcome to LiquidJS!" }}`
 * **Username** is the variable
 * **Append** is adding something (a string) after the variable
  * You can have **multiple** fillers for a single tag.
   * | (vertical bar) is always _before_ a filler.
    * Strings are probably _text that comes after the variable._
* **Assign**: Defines a variable that can be used later on.
* `{% assign foo = "FOO" %}` (example)
 * Similar to sprites in javascript.
``` javascript
{% if foo == "FOO" %}
    Variable `foo` equals "FOO"
{% else %}
    Variable `foo` not equals "FOO"
{% endif %}
```
 * Basically `if` `else` statements in javascript.
* The string after each **}** is text that appears if the condition is true.
  * `else` runs if "if" is false.
   * `{% endif %}` ends the `if` `else` statement.
* `if` runs only if a statement is true.
* `unless` runs only if a statement is **not** true. (in place of `if` in `if` `else` statements)
 * `{% endunless %}

 * Operators

 ``` javascript
 ==	equals
!=	does not equal
>	greater than
<	less than
>=	greater than or equal to
<=	less than or equal to
or	logical or
and	logical and
```
 * These are self-explanatory.
  * They are for `if` `else` statements.
* `contains`
 * Checks for the presence of a substring inside another.
* Example:
``` Javascript
 {% if product.title contains "Pack" %}
  This product's title contains the word Pack.
{% endif %}
```
 * The product.title has the word "Pack", so the string appears.
Also works with tags.
``` Javascript
{% if product.tags contains "Hello" %}
  This product has been tagged with "Hello".
{% endif %}
```
* If tags are not defined with a boolean operator, the string will always appear.

* Hyphens
* `{- tag -}` `{{%- variable -}}`
 * Deletes all empty whitespace.
 Fillers and tags that are specifically made for Jekyll.
* [Jekyll fillers](https://jekyllrb.com/docs/liquid/filters/)
* [Jekyll tags](https://jekyllrb.com/docs/liquid/tags/)
###### Fillers:
* `| append: "text"` adds "text" **after** your variable. (Can also be a variable)
* `| prepend: "text"` adds text **before** your variable. (Can also be a variable)
* `| capitalize` Makes the first letter of your string capital and the rest lowercase.
* `| abs` Makes a number the _absolute value_ (positive)
* `| at_least: 5` Sets a minimum value for a number.
* `| at_most: 5` Sets a maximum value for a number.
* `| ceil` Rounds a number to the nearest whole number.
* `| date: "%a, %b %d, %y"` Converts a date to another format. (Fri, Jul 17, 15) [Does not need to have all the %variables]
* `| default: true, allow_false: true` Shows the default value if the variable has no assigned value.
 * `allow_false` makes it so that the variable can be false instead of using the default value.
* `| divided_by: 3` Divides a number by another (rounds down) Integer > Integer, Float > Float
* `| times 1.0` Times a number by another. (Also allows an integer to become a float.)
* `| downcase` Makes the entire string lowercase.
* `| escape` Escapes a string by replacing characters with escape sequences (so that the string can be used in a URL, for example) [Doesn't really need to be used]
* `| upcase` Makes all letters uppercase.
* `| uniq` Removes all items in a string that are repeated.
* `| truncatewords: 3` Shortens a string to the amount of words specified (Rest are ...)
* `| sum` Adds all items in an array together. (1 + 1...)
* `| strip.html` Removes all HTML tags from a string.
* `| strip` Removes all whitespace from both left & right sides of a string.
* `| split: ", "` Divides a string into an array (White spaces in between [vertical])
* `| sort_natural` Sorts items in a string by a-z without caring about uppercase and lowercase.
* `| sort` Sorts a-z. Capital > Lowercase.
* `| size` Shows the number of items in a string.
* `| round: 2` Rounds the value of a number to the specified amount of decimal places.
* `| reverse` Reverses the order of items listed in a string.
* `| join: " and "` Adds a " and " between each item.
* `| concat: variable` Basically the `CC` in an email. ("Also add this array in the output.")
#### 3/25/25
`capture` allows you to use multiple variables to make a more complex string.
``` Javascript
{% assign favorite_food = "pizza" %}
{% assign age = 35 %}

{% capture about_me %}
I am {{ age }} and my favorite food is {{ favorite_food }}.
{% endcapture %}

{{ about_me }}
```
Only {{ about_me }} shows as content. (The capture part gives about_me the variables too.)
* `increment`
 * Everytime the variable with this tag `{% increment variable %}` is called with the increment, the count increases by one.
 Does not affect a variable created with `assign` and used as a string.
`elseif`
Adds a second conditional (it's a tag)
* `case` and `when`
Use “when” ‘when’ you use "case".
Case allows you to have different strings depending on the value of the variable.
* Also tested liquid in Jekyll; `if` `else` and `assign`.
 * Don't know how to apply fillers yet.

#### 3/26/25
Did some more liquid testing.

You can't put tags (variables) inside of a string; it can only be text.
For font-matter variables, always do `page.variable`
* Variables can be: `title`, `categories`, `random-name`, or anything.
You can put liquid tags in layouts so that the text will only appear if a 'post' has a certain font-matter.

#### 3/27/25
* Tried out `for loops` with `if` `else` statements.
If you have a spacebar between the name of a category, it becomes two separate ones.
In a `if` `else` statement, the `else` will be repeated based on the number of spaces.
``` javascript
{% for categories in page.categories %}
{% if categories contains "Testing" %}
{{ categories }}
{% else %}
<h3> Does not contain "Testing" </h3>
{% endif %}
{% endfor %}

```
Since it's a `for loop`, it can run multiple times instead of one.
If you add text next to `{{ categories }}`, it can also run multiple times.
 * If only one category meets the requirement, only the one that is true will run the `if` statement, the other will run the `else` statement.

#### 3/28/25
Font-Matter-Defaults:
[https://jekyllrb.com/docs/configuration/front-matter-defaults/](https://jekyllrb.com/docs/configuration/front-matter-defaults/)
``` YAML
defaults:
  -
    scope:
      path: "" # an empty string here means all files in the project
    values:
      type: "posts"
      layout: "post"
```
* **Very Important**
* CONFIG.YML REQUIRES PROPER INDENTATIONS!!!!!
* If it's a single space off, it just won't work at all!!.
* Can also be used to set liquid variables.
Set `path` to an empty string, ("") [makes it select everything.]
* Use `type` to limit it. (2 main types- `pages` and `posts` )
* The layout is your layouts in `_layouts`.
Use quotation marks.

#### 4/2/25
Liquid summary: (In Jekyll)

In Jekyll, liquid is mainly used for `{% include %}`and making layouts using categories/base code.

There doesn't seem to be any way to change the value of a variable using `if``else` statements, which limits the dynamic

 <!--
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
