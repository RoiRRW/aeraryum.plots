---  
layout: single  
title: Blog Articles 
permalink: /blog/  
---  
  
<section class="home-posts">  
{% for post in site.posts %}  
<article class="post-card">  
<header> 
</header>  
<a href="{{ post.url }}">
  <img src="{{ post.header.teaser }}" alt="{{ post.title }}">    
</a>
<h3><a href="{{ post.url }}" class="link-as-text">{{ post.title }}</a></h3>  
<div class="excerpt">  
{% if post.excerpt %}<p class="archive__item-excerpt" itemprop="description">{{ post.excerpt | markdownify | strip_html | truncate: 160 }}</p>{% endif %}
</div>  
<small>
  {% include page__meta.html type=include.type %}
</small>
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

