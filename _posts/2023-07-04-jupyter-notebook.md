---
layout: post
title: a post with jupyter notebook
date: 2023-07-04 08:57:00-0400
description: an example of a blog post with jupyter notebook
tags: formatting jupyter
categories: sample-posts
giscus_comments: true
related_posts: false
---

To include a Jupyter notebook in a post, you can use the following code:

{% raw %}

```liquid
{::nomarkdown}
{% assign jupyter_path = 'assets/jupyter/blog.ipynb' | relative_url %}
{% jupyter_notebook jupyter_path %}
{:/nomarkdown}

```

{% endraw %}

Let's break it down: this is possible thanks to Jekyll Jupyter Notebook plugin that allows you to embed Jupyter notebooks in your posts. It basically calls jupyter nbconvert --to html to convert the notebook to an HTML page and then includes it in the post. Since Kramdown is the default Markdown renderer for Jekyll, we need to surround the call to the plugin with the ::nomarkdown tag so that it stops processing this part with Kramdown and outputs the content as-is.

The plugin takes as input the path to the notebook. If the file does not exist, it will typically show a standard error message, but you can ensure that your users are informed about the attempt to load the notebook with the message that follows:

{::nomarkdown} {% assign jupyter_path = "assets/jupyter/blog.ipynb" | relative_url %} {% jupyter_notebook jupyter_path %} {:/nomarkdown}

Note that the Jupyter notebook supports both light and dark themes.
