---
title: Jupyter book page
date: 2021-12-28
categories:
  - Jekyll
last_modified_at: 2021-12-28
excerpt: Usage on the powerful Jupyter book (instead of the Blog theme - Jekyll)
---

# Notes

The ``title`` param in the ``_toc`` file cannot be applied easily. Currently, the easiest way is just modifies the first heading in the notebook.

# Jupyter notebook page

Similar to the transaltion approach mentioned above, here, since jupyter-book is built for jupyter notebook, we create a new github page and store the notebook there, with a url link in the jekyll points to the notebook github page.

When install jupyter-book, due to proxy address problem, **do not** enable VPN while ``pip install -U jupyter-book``.

The [official docs](https://jupyterbook.org/start/your-first-book.html) contains a lot of explanantion, below is the simplest version.
Below reference from the [simple example](https://github.com/executablebooks/quantecon-mini-example/tree/master/mini_book) structure. [How official docs is formatted](https://github.com/executablebooks/jupyter-book/blob/master/docs/_toc.yml).

> :notes: **Assume knowledge**: have publish gh-pages before.

Note: main branch to store source code, gh-pages for what's published

# Source code

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
# Compile jupyter book

``jupyter-book build ursourcecodeFolder``

# Deployment

[docs folder in main branch is curren appraoch](https://docs.github.com/en/pages/)getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## gh-pages 

Copy the content of the generated ``_build/html`` folder and place it to root of the gh-pages branch (nothing else is needed) and then add a empty file named: ``.nojekyll``, then push it.

Now, add a link from the jekyll page to this notebook page and it's done

To preview the html result, see [preview](https://jupyterbook.org/start/build.html)

# TOC

https://jupyterbook.org/structure/configure.html?highlight=title

# Emoji

Directly copy and paste emoji instead of use the syntax which is doable in Jekyll.
For window, do ``window key + ;``