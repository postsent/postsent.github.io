---
title: "My customerisation on Keykll themes"
date: 2021-12-11
categories:
  - Jeykll
toc: true
toc_sticky: true
last_modified_at: 2021-12-22
---
# Compare different themes - Blog:

> :eyes: **Notes**: Easiest way to find the popular ones, search the theme, then sort by stars/forks on github

Hexo:
- [Hexo example](http://monkeywie.cn/categories/)
  
Jeykll:
- [minimal mistake](https://fortierq.github.io/)
- [clean](https://tianqi.name/jekyll-TeXt-theme/test/)

Hugo:

- [Docs like](https://www.linode.com/docs/)

Others:
- [disable copy and paste](https://7988888.xyz/blog1/)
  
# Minimal Mistake - References post
Different examples/edge cases's code see [minimal repo docs folder](https://github.com/mmistakes/minimal-mistakes/tree/master/docs)
For actual output, search in the [quick start](https://mmistakes.github.io/minimal-mistakes/) with the corresponding title.

E.g [header image code](https://raw.githubusercontent.com/mmistakes/minimal-mistakes/master/docs/_posts/2012-03-15-layout-header-image-text-readability.md) with [header image visual output](https://mmistakes.github.io/minimal-mistakes/layout-header-image-text-readability/)
# Notes
## Header image
the path for files in the _{folderName} those with underscore, then the image path is always: ``/assets/images/lost-function.png`` i.e. starting from the **root folder**.
> :eyes: Note that the root level base reference does not work if u add a baseurl e.g. ``/cn``. In the case of base url, use ``{{ site.baseurl }}/assets/images/urimagefileName``
## Excerpt
Excerpt (the text display as a preview in e.g. the post by year page) if defined, will override the tagline (the text display in the overlay image under the title). 

[Notebook layout](https://fortierq.github.io/nb/svm/)
# Font size
[global font size depends on screen width](https://github.com/mmistakes/minimal-mistakes/issues/1043)
```scss
// Modified files: _sass/minimal-mistakes/_reset.scss
  @include breakpoint($medium) {
    // font-size: 18px;
    font-size: 12px;
  }

  @include breakpoint($large) {
    // font-size: 20px;
    font-size: 14px;
  }

  @include breakpoint($x-large) {
    // font-size: 22px;
    font-size: 16px;
  }

  -webkit-text-size-adjust: 100%;
  -ms-text-size-adjust: 100%;
}

```
Notes:
* yaml file -  quote for str may not necessary.

# Remove left sidebar completely for posts

[links](https://github.com/mmistakes/minimal-mistakes/issues/1322)

```scss
.page {
  @include breakpoint($large) {
    float: right;
    // width: calc(100% - #{$right-sidebar-width-narrow});
    width: 94%; // just fit into one page, if 93% then slight wider than one page on my screen
    padding-right: $right-sidebar-width-narrow;
  }

  @include breakpoint($x-large) {
    // width: calc(100% - #{$right-sidebar-width});
    width: 94%;
    padding-right: $right-sidebar-width;
  }
  // change the width for .page__related as well
```
After this, if you want to set up a page like [docs](https://mmistakes.github.io/minimal-mistakes/docs/collections/) then you need to create a different layout html for the page format (otherwise, the sidebar and the page will overlap) since the above 94% width is fixed unlike the previous setting which taking into account of the sidebar width.   

To fix this, create a new html called e.g. ``page_sidebar.html``in _layout by copying the single.html. Then change the ``class="page`` to ``class="page_sidebar`` and decorate this new class at ``_page.scss`` with ``.page_sidebar``, similar to above, but a different class name and with the old setting which is ``width: calc(100% - #{$right-sidebar-width});``. 

Then applies this ``layout: page_sidebar`` to all the collection e.g. _docs for the case in the official theme docs.  
Don't forget to add the collection in the ``_config.yml`` as mentioned in [Working with Collections](https://mmistakes.github.io/minimal-mistakes/docs/collections/) with the rest follow the [sidebar](https://mmistakes.github.io/minimal-mistakes/docs/layouts/#sidebars)
# Add favicon.con in the tab & masthead
change ``logo`` param in the _config.yml will do for the masthread
TODO: insert result image here (top-left appears img)
```html
# location: _includes\head\custom.html
<link rel="icon" type="image/png" sizes="32x32" href="/assets/images/favicon.ico">
```
TODO: insert result image here

# Header image size
[overlay vs normal header image size](https://github.com/mmistakes/minimal-mistakes/issues/542)
[Header image is scaled based on screen width and not easy to change](https://github.com/mmistakes/minimal-mistakes/issues/2107)
Solution - just use overlay_image which gives a smaller header image size by default
```yml
title: Home
tagline: "Weclome to my blog"
header:
    overlay_image: "/assets/images/wild.jpg"
    caption: "Photo credit: [**Wadim Kashin**](https://septicwd.tumblr.com/)"
```
# Inspiration
Below are list of blog examples using Jekyll theme
[mincong](https://mincong.io/en/archive/)
code example

[fortierq](https://fortierq.github.io/python-import/)

# Archive page design
[ultimate](https://talk.jekyllrb.com/t/displaying-archives-design-ideas/2330)
[ok](https://esthermakes.tech/blog/2020/04/09/creating-category-pages-with-jekyll/)

## tags
```scss
// Based on: https://www.designlabthemes.com/css-tags-how-to-style-post-tags/)
// file: _sass\minimal-mistakes\_page.scss and change .taxonomy__index
// a {
    //   display: -webkit-box;
    //   display: -ms-flexbox;
    //   display: flex;
    //   padding: 0.25em 0;
    //   -webkit-box-pack: justify;
    //   -ms-flex-pack: justify;
    //   justify-content: space-between;
    //   color: inherit;
    //   text-decoration: none;
    //   border-bottom: 1px solid $border-color;
    // }
  a {
    // display: inline-block;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-pack: justify;
    -ms-flex-pack: justify;
    justify-content: space-between;
    height: 24px;
    line-height: 24px;
    position: relative;
    margin: 0 16px 8px 0;
    padding: 0 10px 0 12px;
    // background: #23f368;
    background-image:url('/assets/images/leaf.jpg'); // background color from image
    // Below make the corner rounded instead of sharpe
    -webkit-border-bottom-right-radius: 3px;    
    border-bottom-right-radius: 3px;
    -webkit-border-top-right-radius: 3px;    
    border-top-right-radius: 3px;
    -webkit-border-bottom-left-radius: 3px;    
    border-bottom-left-radius: 3px;
    -webkit-border-top-left-radius: 3px;    
    border-top-left-radius: 3px;
    //
    -webkit-box-shadow: 0 1px 2px rgba(0,0,0,0.2);
    box-shadow: 0 1px 2px rgba(0,0,0,0.2);
    color: rgb(12, 0, 177); // tag text color
    font-size: 12px;
    font-family: "Lucida Grande","Lucida Sans Unicode",Verdana,sans-serif;
    text-decoration: none;
    text-shadow: 0 1px 2px rgba(0,0,0,0.2);
    text-indent: 2px; // move text to right a bit
    font-weight: bold;
  }
  // below  decorate the hole in the tag
  a:after {
    content: "";
    position: absolute;
    top: 10px;
    left: 3px; // tag's hole position to left
    float: left;
    width: 5px;
    height: 5px;
    -webkit-border-radius: 50%;
    border-radius: 50%;
    background: #fff;
    -webkit-box-shadow: -1px -1px 2px rgba(0,0,0,0.4);
    box-shadow: -1px -1px 2px rgba(0,0,0,0.4);
    }
  }
```
# Simple language switcher - text form
```html
<!-- location: _includes\page__meta.html before the end </p> -->
<span class="page__meta-sep"></span>
    {% assign current_url = page.url %}
    <a href="http://localhost:4000/cn{{ current_url }}" style="color:#FF0000;">CN/中文</a>
```
Also, in the ``_config.yml``, I chaneg the url format to below which is simpler than the category/filetitle format since I want to translate the category and if I use category in the url, I have to map each english url to chinese one which takes time, but if use the filename, then I just need to keep the filename the same and add a prefix i.e. ``/en`` or ``/cn`` to switch between langauage.
```yml
permalink: /:year/:month/:day/:title/ # /:categories, https://jekyllrb.com/docs/permalinks/
```
Also, I set the baseurl to ``/en`` or ``/cn``, just to make sure it does not confuse with other project github page url.

## Automated translation for yml file
Below is applied to _config.yml
```py
"""
https://stackoverflow.com/questions/7255885/save-dump-a-yaml-file-with-comments-in-pyyaml/27103244

Possible improvement for below: merge two yml file
https://stackoverflow.com/questions/58500491/merge-yaml-files-with-overriding-values-in-list-elements
"""
import sys
import ruamel.yaml

def changes(c):
    c['locale'] = 'zh'
    c['title'] = 'Jerry的博客'
    c['description'] = 'Jerry的博客 - Jekyll主题'
    c['baseurl'] = '/cn'
    c['repository'] = 'postsent/cn'
    c['masthead_title'] = 'Jerry的博客'
    a = c['author']
    a['location'] = '悉尼/深圳'
    d = c['defaults']
    d[0]['values']['toc_label'] = '目录'
    
with open("original.yml", "r") as stream:
    
    yaml = ruamel.yaml.YAML()  # defaults to round-trip if no parameters given
    code = yaml.load(stream)
    changes(code)
    yaml.indent(mapping=2, sequence=4, offset=2)
    with open("new.yml", "w") as f:
        yaml.dump(code, f)
```
# Apply to all by specifing paths in config.yml
```yml
defaults:
- scope:
      path: '_posts/ml' # this is the folder that I want to apply the same header images to 
      type: posts
  values:
    layout: single
    author_profile: true
    header:
      overlay_image: "./assets/images/ai.jpg"
      caption: 'Photo credit: [**winxtech**](https://winxtech.com/machine-learning-services)'
```
# Emoji
Add plugin [jemoji](https://github.com/jekyll/jemoji) which is officially supported on Github Page

# Display jupyter notebook page
Similar to the transaltion approach mentioned above, here, since jupyter-book is built for jupyter notebook, we create a new github page and store the notebook there, with a url link in the jeykll points to the notebook github page.

When install jupyter-book, due to proxy address problem, **do not** enable VPN while ``pip install -U jupyter-book``.

The [official docs](https://jupyterbook.org/start/your-first-book.html) contains a lot of explanantion, below is the simplest version.
Below reference from the [simple example](https://github.com/executablebooks/quantecon-mini-example/tree/master/mini_book) structure.
> :notes: **Assume knowledge**: have publish gh-pages before.

Note: main branch to store source code, gh-pages for what's published

## Source code
Configure you main branch as below.
Fill in the ``_config`` & ``_toc`` as above example (replaced with ur file structure).
More details can be found in the official docs e.g. [toc](https://jupyterbook.org/customize/toc.html)
Source code structure:
```
├── _config.yml
├── _toc.yml
├── notebooksFolder
│   ├──notebook1.ipynb
│   ├──...
```
## Compile jupyter book
``jupyter-book build ursourcecodeFolder``

## gh-pages 

Copy the content of the generated ``_build/html`` folder and place it to root of the gh-pages branch (nothing else is needed) and then add a empty file named: ``.nojekyll``, then push it.

Now, add a link from the jeykll page to this notebook page and it's done

To preview the html result, see [preview](https://jupyterbook.org/start/build.html)
# Minor

## Remove toc border

```scss
// location: _sass\minimal-mistakes\_navigation.scss
.toc {
  font-family: $sans-serif-narrow;
  color: $gray;
  background-color: $background-color;
  // border: 1px solid $border-color;
  // border-radius: $border-radius;
  border: none !important;
```
Add top padding between the page meta e.g. reading time in a post to the above title

```scss
// location: _sass\minimal-mistakes\_page_.scss
.page__meta {
    margin-top: 2em;
    padding-top: 10px;
```
## Change code snippet color

[Different style](https://mmistakes.github.io/minimal-mistakes/docs/stylesheets/)
```scss
// location: assets\css\main.scss
@import "minimal-mistakes/skins/{{ site.minimal_mistakes_skin | default: 'default' }}"; // skin

$base00: #263238; 
$base01: #2e3c43;
$base02: #314549;
$base03: #546e7a;
$base04: #b2ccd6;
$base05: #eeffff;
$base06: #eeffff;
$base07: #ffffff;
$base08: #f07178;
$base09: #f78c6c;
$base0a: #ffcb6b;
$base0b: #c3e88d;
$base0c: #89ddff;
$base0d: #82aaff;
$base0e: #c792ea;
$base0f: #ff5370;
```

## Multiple urls for one page
Follow [jekyll-redirect-from plugin](https://github.com/jekyll/jekyll-redirect-from).

## A run script 

```bash
# this allows changes at real time
bundle exec jekyll serve --force_polling --port 4000
```

## Baidu SEO verification

[reference](https://blog.csdn.net/torpidcat/article/details/120222387)

## Separation between technical & casual

Use different collections, the existing category is used for CS related whilst tag is used for casual stuffs.