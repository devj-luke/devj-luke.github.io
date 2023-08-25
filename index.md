---
layout: default
---
<ul>
  {% for post in site.posts %}
    <li>
      <h4><a class="index-post" href="{{ post.url }}"><span class="index-date">{{ post.date | date: "%Y-%m-%d" }} | </span><span class="index-title">{{ post.title }}</span></a></h4>
    </li>
  {% endfor %}
</ul>
