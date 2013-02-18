---
layout: page
title: 最新文章列表
---

## 最新文章

* hello.html
{% for post in sites.posts %}
* {{ post.date | date_to_string }} [{{ post.title }}]({{ site.baseurl }}{{ post.url }})
{% endfor %}
