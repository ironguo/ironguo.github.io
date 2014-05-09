---
layout: page
title: "Blog"
tagline: 一个努力敲击键盘的码农（My blog）
---
{% include JB/setup %}

[Jekyll Bootstrap快速入门](http://jekyllbootstrap.com/usage/jekyll-quick-start.html)
官方文档: [Jekyll Bootstrap](http://jekyllbootstrap.com)

<ul class="posts">
  {% for post in site.posts %}
    <li><a href="{{ BASE_PATH }}{{ post.url }}"><h4>{{ post.title }}</h4></a></li>
    <li>{{ post.excerpt }}</li>
  {% endfor %}
</ul>
