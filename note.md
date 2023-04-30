---
layout: page
title: 笔记
subtitle: 
---

<div>
{% assign postsNotes = site.posts | "post.notes"  %}
{% for note in postsNotes %}
<h4 class="post-teaser__month">
<strong>
{% if note.name %} 
- - - - -  {{ note.name }} - - - - - 
{% else %} 
{{ Print }} 
{% endif %}
</strong>
</h4>
<ul class="list-posts">
{% for post in note.items %}
<li class="post-teaser">
<a href="{{ post.url | prepend: site.baseurl }}">
<span class="post-teaser__title">{{ post.title }}</span>
<span class="post-teaser__date">{{ post.date | date: "%d %B %Y" }}</span>
</a>
</li>
{% endfor %}
</ul>
{% endfor %}
</div>