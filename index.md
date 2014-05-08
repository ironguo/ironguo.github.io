---
layout: page
title: "看门大叔"
tagline: ~ 一个努力敲击键盘的码农（My blog）
---
{% include JB/setup %}

[Jekyll Bootstrap快速入门](http://jekyllbootstrap.com/usage/jekyll-quick-start.html)

官方文档: [Jekyll Bootstrap](http://jekyllbootstrap.com)

### 作者信息

在 `_config.yml` 文件中填写你自己的信息:
    
    title : My Blog =)   
    author :
      name : Name Lastname
      email : blah@email.test
      github : username
      twitter : username

主题模版需要时，可引用这些变量值。
    
### 示例文件

本博客包含一个示例文件。
如果你不需要，可删除文件夹 `_posts/core-samples`。

    $ rm -rf _posts/core-samples

示例 "博客帖子列表"。

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
