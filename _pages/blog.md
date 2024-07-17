---
title: "Blog"
permalink: /blog/
layout: splash
classes: wide
---
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      <p>{{ post.excerpt }}</p>
    </li>
  {% endfor %}
</ul>

<div class="container">
  {% for post in site.posts %}
  <div class="row">
    <div class="col">
      <li>
        <a href="{{ post.url }}">{{ post.title }}</a>
        <p>{{ post.excerpt }}</p>
      </li>
    </div>
  </div>
  {% endfor %}
</div>
