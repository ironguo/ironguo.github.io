---
layout: page
title: "Blog"
tagline: "一个努力敲击键盘的码农（My blog）"
keywords: "博客,互联网,电子商务,开源,程序员,PHP,PHP框架"
description: "个人博客ironguo.github.io，从事互联网行业，PHP程序员一个，效忠开源，乐于钻研框架。"
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
