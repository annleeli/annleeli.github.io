---
layout: page
title: Archive
published: true
---

{% for post in site.posts %}

{% unless post.next %}
<h2>{{ post.date | date: '%Y' }}</h2>

{% else %}
{% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
{% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
{% if year != nyear %}
<h2>{{ post.date | date: '%Y' }}</h2>
<ul>
{% endif %}
{% endunless %}

<li>{{ post.date | date:"%b" }} <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>