---
layout: page
title: 总览
subtitle: 
permalink: /blog/
---

<!-- <div>
{% assign postsCategory = site.posts | group_by_exp:"post", "post.categories"  %}
{% for category in postsCategory %}
<h4 class="post-teaser__month">
<strong>
{% if category.name %} 
- - - - -  {{ category.name }} - - - - - 
{% else %} 
{{ Print }} 
{% endif %}
</strong>
</h4>
<ul class="list-posts">
{% for post in category.items %}
<li class="post-teaser">
<a href="{{ post.url | prepend: site.baseurl }}">
<span class="post-teaser__title">{{ post.title }}</span>
<span class="post-teaser__date">{{ post.date | date: "%d %B %Y" }}</span>
</a>
</li>
{% endfor %}
</ul>
{% endfor %}
</div> -->

<ul>
  {% for post in site.posts %}

    {% unless post.next %}
      <h2>{{ post.date | date: '%Y年' }}</h2>
    {% else %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        <h2>{{ post.date | date: '%Y年' }}</h2>
      {% endif %}
    {% endunless %}

    <li>{{ post.date | date:"%Y年%m月%d日：" }} <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>