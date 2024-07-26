---  
layout: splash  
title: Blog  
permalink: /blog/  
---  
  
<section class="home-posts">  
{% for post in site.posts %}  
<article class="post-card">  
<header>  
<img src="{{ post.header.teaser }}" alt="{{ post.title }}">  
<h2><a href="{{ post.url }}">{{ post.title }}</a></h2>  
</header>  
<div class="excerpt">  
{{ post.excerpt | truncatewords: 50 }}  
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

