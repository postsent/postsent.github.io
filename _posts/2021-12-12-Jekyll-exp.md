---
# layout: posts
title: "My experience so far with Jukyell"
date: 2021-12-12
categories:
  - blog
tags:
  - Jekyll
toc: true
toc_sticky: true
---

# Progress
1. Go through the configuration site
   https://mmistakes.github.io/minimal-mistakes/docs/configuration/
2. Set up langauge switcher by simply create two differetn github.io pages - one personal, one project.
The pros is little dependency between two language versino of the websites, e.g. could make two completely different _congfig.yml & navigation.yml (structure) file. 
A lot less complexity compared with current approach, see the disucssion in the github issues in the minimal mistake github page. E.g. If use third-party plugin - multi-language Jeykll, currently is not supported by the github page due to security.
Cons: The method is navie.
3. Change the locale (language setting) depends on chinese or english.  

After some days of struggling in incoperating the teXt-theme(simple, clean and modern lookng) archive page into this theme(well-maintain, cross-platform e.g. great mobile support e.g. when small screen the toc is placed on the top of the page). To see how well-maintain, check number of issues opened in a GitHub page.
# Edge cases
Long TOC title.
Long category title in category page.
# Notes
**_data/navigation.yml**
* The masthead links use a “priority plus” design pattern. Meaning, show as many navigation items that will fit horizontally with a toggle to reveal the rest.
* Default url format: category/fileNameSubfix e.g. year-mm-dd-{fileNameSubfix}, with category defined in the meta of md file
* Put the most important links first so they’re always visible and not hidden behind the menu toggle.
* This ``description`` param will show up like a tooltip, when the user hovers over the link on a desktop browser
* [sample post](https://mmistakes.github.io/minimal-mistakes/layout-table-of-contents-sticky/)
* [source code](https://github.com/mmistakes/minimal-mistakes/blob/master/docs/_posts/2012-01-03-layout-table-of-contents-sticky.md)

Note below type:posts refers to the _posts folder, can be customised
```yaml
defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      ...
```

[Below is Backlog/todo](https://mmistakes.github.io/minimal-mistakes/docs/configuration/)


# Done
- [x] Comments - use utterance since uses github issue api. Other, either requires dependencies too much or has ads (free version). Cons: users need to login to comment
- [X] Google search console
- [X] Site Author
- [X] google anaylytics # freemium
- [X] Timezone
- [X] toc_sticky

# Revisited
- [ ] Front Matter Defaults
  -  default permalink style used by the theme is permalink: ``/:categories/:title/``
- [ ] [UI Text in different language](https://mmistakes.github.io/minimal-mistakes/docs/ui-text/)
- [ ] [Single layout](https://mmistakes.github.io/minimal-mistakes/docs/layouts/)
- [ ] group by - layout: posts, categories, collection(group by custom e.g. receipe type), etc
- [ ] Helpers
- [ ] Utility Classes

# Standard
- [ ] show_date: true
- [ ] add to defaults in _config.yml for global setting
- [ ] Custom head and footer
- [ ] paginate: how many recent posts shown in home page
- [ ] data_format
- [ ] social profile
- [ ] excerpt: override meta description with SEO benefits
- [ ] social media icon - e.g. [Reddit icon](https://mmistakes.github.io/minimal-mistakes/docs/layouts/#wide-page)

# More

- [ ] breadcrumbs
- [ ] Headers e.g. images in the head of a post, Header overlay (text on images)
- [ ] search: false - exclude page/post being indexed
- [ ] Canonical URL
- [ ] HTML compression - performance
- [ ] Page meta separator
- [ ] algolia (faster search api)
- [ ] Google Analytics (failed)
- [ ] Paginate (change #pages shown in home)
- [ ] Archive settings

# Something stupid

Maintain two version of the website in two languages can be fun/tidious.  
Currrently maintain two local, two remote themes for english and chinese.  
Why? To keep github with as less unneccessary files as possible. The remote them supply the js/css stuffs and so only e.g. _posts,_pages and stuffs need to be rewrited e.g _layout folder is needed.  

Once, I accidentally change the chinese version when I mean the english one.  
Then, I change the English remote version instead of english local version. 