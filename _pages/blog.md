---
title: "Blog"
permalink: /blog/
layout: splash
classes: wide
---
{% for post in site.posts %}
<div class="col-sm-4">
  <div class="card" style="width: 20rem;">
    <img class="card-img-top" src=post.header.teaser>
    <div class="card-block">
      <h4 class="card-title">{{ post.title }}</h4>
      <p class="card-text">{{ post.category }}</p>
    </div>
  </div>
</div>
{% endfor %}


<ul>    
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">
        {{ post.title }}
      </a>
      - <time datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date_to_long_string }}</time>
    </li>
  {% endfor %}
</ul>
