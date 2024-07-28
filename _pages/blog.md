---  
layout: single  
title: Blog Articles 
permalink: /blog/  
---  
  
<section class="home-posts">  
{% for post in site.posts %}  
<article class="post-card">  
<header>  
<img src="{{ post.header.teaser }}" alt="{{ post.title }}">  
<h2><a href="{{ post.url }}" style="text-decoration:none; color: #000;">{{ post.title }}</a></h2>  
{% include page__meta.html type=include.type %}
</header>  
<div class="excerpt">  
{% if post.excerpt %}<p class="archive__item-excerpt" itemprop="description">{{ post.excerpt | markdownify | strip_html | truncate: 160 }}</p>{% endif %}
</div>  
</article>  
{% endfor %}  
</section>  
  
<div class="pagination">  
{% if paginator.total_pages > 1 %}  
<ul>  
{% for page in (1..paginator.total_pages) %}  
<li><a href="{{ site.baseurl }}/blog/page/{{ page }}">{{ page }}</a></li>  
{% endfor %}  
</ul>  
{% endif %}  
</div>  

