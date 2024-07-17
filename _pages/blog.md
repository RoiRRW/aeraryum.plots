---
title: "Blog"
permalink: /blog/
layout: splash
classes: wide
---




<div class="container">
{% assign nbr_col = 3 %}
{% assign loopindex = 0 %}
{% for page in site.pages %}
  {% if post.header.teaser %}
    {% capture teaser %}{{ post.header.teaser }}{% endcapture %}
  {% else %}
    {% assign teaser = site.teaser %}
  {% endif %}    
  {% if post.id %}
    {% assign title = post.title | markdownify | remove: "<p>" | remove: "</p>" %}
  {% else %}
    {% assign title = post.title %}
  {% endif %}
  {% assign rowfinder = loopindex | modulo: 3 %}
  {% assign loopindex = loopindex | plus: 1 %}
  {% if rowfinder == 0 %}
    <div class="row">
      <div class="col-sm-4">
        <article class="archive__item" itemscope itemtype="https://schema.org/CreativeWork"{% if post.locale %} lang="{{ post.locale }}"{% endif %}>
          <div class="archive__item-teaser">
            <img src="{{ teaser | relative_url }}" alt="">
          </div>
          <h2 class="archive__item-title no_toc" itemprop="headline">
            {% if post.link %}
              <a href="{{ post.link }}">{{ title }}</a> <a href="{{ post.url | relative_url }}" rel="permalink"><i class="fas fa-link" aria-hidden="true" title="permalink"></i><span class="sr-only">Permalink</span></a>
            {% else %}
              <a href="{{ post.url | relative_url }}" rel="permalink">{{ title }}</a>
            {% endif %}
          </h2>
          {% include page__meta.html type=include.type %}
          {% if post.excerpt %}<p class="archive__item-excerpt" itemprop="description">{{ post.excerpt | markdownify | strip_html | truncate: 160 }}</p>{% endif %}
        </article>      
      </div>    
  {% elsif rowfinder == 2 %}
    <div class="col-sm-4">
      <article class="archive__item" itemscope itemtype="https://schema.org/CreativeWork"{% if post.locale %} lang="{{ post.locale }}"{% endif %}>
        <div class="archive__item-teaser">
          <img src="{{ teaser | relative_url }}" alt="">
        </div>
        <h2 class="archive__item-title no_toc" itemprop="headline">
          {% if post.link %}
            <a href="{{ post.link }}">{{ title }}</a> <a href="{{ post.url | relative_url }}" rel="permalink"><i class="fas fa-link" aria-hidden="true" title="permalink"></i><span class="sr-only">Permalink</span></a>
          {% else %}
            <a href="{{ post.url | relative_url }}" rel="permalink">{{ title }}</a>
          {% endif %}
        </h2>
        {% include page__meta.html type=include.type %}
        {% if post.excerpt %}<p class="archive__item-excerpt" itemprop="description">{{ post.excerpt | markdownify | strip_html | truncate: 160 }}</p>{% endif %}
      </article>      
    </div>    
    </div>
  {% else %}
    <div class="col-sm-4">
      <article class="archive__item" itemscope itemtype="https://schema.org/CreativeWork"{% if post.locale %} lang="{{ post.locale }}"{% endif %}>
        <div class="archive__item-teaser">
          <img src="{{ teaser | relative_url }}" alt="">
        </div>
        <h2 class="archive__item-title no_toc" itemprop="headline">
          {% if post.link %}
            <a href="{{ post.link }}">{{ title }}</a> <a href="{{ post.url | relative_url }}" rel="permalink"><i class="fas fa-link" aria-hidden="true" title="permalink"></i><span class="sr-only">Permalink</span></a>
          {% else %}
            <a href="{{ post.url | relative_url }}" rel="permalink">{{ title }}</a>
          {% endif %}
        </h2>
        {% include page__meta.html type=include.type %}
        {% if post.excerpt %}<p class="archive__item-excerpt" itemprop="description">{{ post.excerpt | markdownify | strip_html | truncate: 160 }}</p>{% endif %}
      </article>      
    </div>    
  {% endif %}
{% endfor %}
{% if rowfinder != 2 %}
  </div>
{% endif %}
</div>








