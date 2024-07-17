---
permalink: /stocks/
layout: splash
---
<div class="row">
    <div class="col">
    {% for post in site.posts %}
      <li class="post-item">
        <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">
          <div class="post-info">
            <p>Post #1</p>
            <h2>{{ post.title }}</h2>
          </div>
        </a>
      </li>
    {% endfor %}
  </div> 
</div> 
