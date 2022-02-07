---
title: "My markdown cheatsheet"
date: 2021-12-14
categories:
  - Cheatsheet
toc: true
toc_sticky: true
---

# Insert images
```html
<!-- simple -->
<img src="/assets/images/test.jpg" width="1000"  height="300" />
<!-- Aspect ratio -->
<img src="/assets/images/test.jpg" width="50%"/>
<!-- with caption -->
<figure align="center">
<img src="/assets/images/4920-ethics-kant-mill.png" alt="image" />
<figcaption align="center">This is my caption text.</figcaption>
</figure>
<!-- The ALT text adds a text description to an image on a Web page -->
<!-- this one can centre in jekyll, note that using this syntax, only width will take effect and the ratio is remained -->
<p align="center">
<img src="/assets/images/unsw-courses/2511-1.png" alt="drawing" width="500"/>
</p>
```
<figure align="center">
<img src="/assets/images/test.jpg" alt="image" width="600" height="300" />
<figcaption align="center">This is my caption text.</figcaption>
</figure>
# Table
```
<!-- with  bullet points -->
| Course |  Comments                       |  
|:-------| :---------------------------    | 
|...     |<ul><li> ...</li><li>...</li><ul>| 
```

| Fruit   | Price  | Advantages                        |  
| ------- | ------ | --------------------------------- |  
| Bananas | $1.34  | {::nomarkdown}<ul><li>built-in wrapper</li><li>bright color</li></ul>{:/} |  
| Oranges | $2.10  | {::nomarkdown}<ul><li>cures scurvy</li><li>tasty</li></ul>{:/} |  

# Emoji
[github Link](https://gist.github.com/rxaviers/7360908#file-gistfile1-md)
[gitlab link](https://github.com/yodamad/gitlab-emoji)
> :warning: **If you are using mobile browser**: Be very careful here!

# Hidden list
```html
<details>
<summary markdown="span">Click to expand/hide</summary>
123
</details>
```
<details>
<summary markdown="span">Click to expand/hide</summary>
123
</details>

# Folder structure
```
├── 1
│   ├── 2
|   |   ├──3
|   |   |   ├──4
```

# Minor

## Newline
```html
<br />
```

# Jekyll 

# Code snippet in Collispable section

```html
<!-- note below use the raw tag, to escape the liquid tags see:  https://stackoverflow.com/questions/3426182/how-to-escape-liquid-template-tags-->
<details>
<summary markdown="span" style="color:blue;">Code</summary>
{% raw  %}
{% highlight python %}
print("hello world")
{% endhighlight %}
{% endraw %}
</details>
```

<details>
<summary markdown="span" style="color:blue;">Here is the output of above code</summary>

{% highlight python %}
print("hello world")
{% endhighlight %}
</details>




