---
layout: page
title: 전체 글
permalink: /archive/
---
<article>

<!-- from http://www.mitsake.net/2012/04/archives-in-jekyll/ -->

{% for post in site.posts %}
{% capture month %}{{ post.date | date: '%m%Y' }}{% endcapture %}
{% capture nmonth %}{{ post.next.date | date: '%m%Y' }}{% endcapture %}
{% if month != nmonth %}
{% if forloop.index != 1 %}</ul>{% endif %}
<h3>{{ post.date | date: '%Y년 %m월' }}</h3><ul>
{% endif %}
<li> <a href="{{ post.url }}">{{ post.title }}</a>  <span class="date">{{ post.date | date: "%Y-%m-%d" }}</span><br><div>
    <ul class="tags post-tags cf">
      <li>Tagged:</li>
      {% for tag in page.tags %}
      <li><a href="/search/?tags={{ tag }}">{{ tag | downcase }}</a></li>
      {% endfor %}
    </ul>
  </div><</li>
 
{% endfor %}