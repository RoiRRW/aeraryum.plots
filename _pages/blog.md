---
title: "Blog"
permalink: /blog/
layout: splash
classes: wide
---
{% for post in site.posts limit:9 %}
<div class="col-sm-4">
  <div class="card" style="width: 20rem;">
    <img class="card-img-top" src="../media/logo-prueba.jpg">
    <div class="card-block">
      <h4 class="card-title">{{ post.title }}</h4>
      <p class="card-text">{{ post.category }}</p>
    </div>
  </div>
</div>
{% endfor %}
