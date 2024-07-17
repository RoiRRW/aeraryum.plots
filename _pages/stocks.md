---
permalink: /stocks/
layout: splash
---
<div class="container">
<div class="row">
    {% for post in site.posts %}
    <div class="col">
      <li class="post-item">
        <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">
          <div class="post-info">
            <p>Post #1</p>
            <h2>{{ post.title }}</h2>
          </div>
        </a>
      </li>
    </div> 
  {% endfor %}
</div> 
</div>
