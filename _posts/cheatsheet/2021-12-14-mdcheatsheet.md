---
title: "My markdown cheatsheet"
date: 2021-12-14
categories:
  - cheatsheet
toc: true
toc_sticky: true
---

# Insert images
```html
<!-- simple -->
<img src="../../assets/images/test.jpg" alt="image" width="1000"  height="300" />
<!-- with caption -->
<figure align="center">
<img src="../../assets/images/4920-ethics-kant-mill.png" alt="image" />
<figcaption align="center">This is my caption text.</figcaption>
</figure>
<!-- The ALT text adds a text description to an image on a Web page -->
```
<figure align="center">
<img src="../../assets/images/test.jpg" alt="image" width="600" height="300" />
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
[github Link](https://gist.github.com/roachhd/1f029bd4b50b8a524f3c)
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

# Jeykll 
# Code snippet in Collispable section
```html
<details>
<summary markdown="span" style="color:blue;">Code</summary>

{% highlight python %}
print("hello world")
{% endhighlight %}
</details>
```

<details>
<summary markdown="span" style="color:blue;">Code</summary>

{% highlight python %}
print("hello world")
{% endhighlight %}
</details>




