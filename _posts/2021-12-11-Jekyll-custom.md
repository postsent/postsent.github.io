---
title: "My customerisation on Keykll themes"
date: 2021-12-11
categories:
  - blog
tags:
  - Jekyll
toc: true
toc_sticky: true
---
# references post
Different examples/edge cases's code see [minimal repo docs folder](https://github.com/mmistakes/minimal-mistakes/tree/master/docs)
For actual output, search in the [quick start](https://mmistakes.github.io/minimal-mistakes/) with the corresponding title.
E.g [header image code](https://raw.githubusercontent.com/mmistakes/minimal-mistakes/master/docs/_posts/2012-03-15-layout-header-image-text-readability.md) with [header image visual output](https://mmistakes.github.io/minimal-mistakes/layout-header-image-text-readability/)
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

# archive page design
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
      background: rgb(252, 162, 77);    
      -webkit-border-bottom-right-radius: 3px;    
      border-bottom-right-radius: 3px;
      -webkit-border-top-right-radius: 3px;    
      border-top-right-radius: 3px;
      -webkit-box-shadow: 0 1px 2px rgba(0,0,0,0.2);
      box-shadow: 0 1px 2px rgba(0,0,0,0.2);
      color: #fff;
      font-size: 12px;
      font-family: "Lucida Grande","Lucida Sans Unicode",Verdana,sans-serif;
      text-decoration: none;
      text-shadow: 0 1px 2px rgba(0,0,0,0.2);
      font-weight: bold;
    }
    a:before {
      content: "";
      position: absolute;
      top:0;
      left: -12px;
      width: 0;
      height: 0;
      border-color: transparent #fca24d transparent transparent;
      border-style: solid;
      border-width: 12px 12px 12px 0;  
      }
  
    a:after {
      content: "";
      position: absolute;
      top: 10px;
      left: 1px;
      float: left;
      width: 5px;
      height: 5px;
      -webkit-border-radius: 50%;
      border-radius: 50%;
      background: #fff;
      -webkit-box-shadow: -1px -1px 2px rgba(0,0,0,0.4);
      box-shadow: -1px -1px 2px rgba(0,0,0,0.4);
      }
```
# Simple language switcher - text form
```html
<!-- location: _includes\page__meta.html before the end </p> -->
<span class="page__meta-sep"></span>
    {% assign current_url = page.url %}
    <a href="http://localhost:4000/cn{{ current_url }}" style="color:#FF0000;">CN/中文</a>
```
