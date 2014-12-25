---
layout: page
title: Archive
published: true
---

{% for post in site.posts %}
{% capture currentyear %}{{post.date | date: "%Y"}}{% endcapture %}
  {% if currentyear != year %}
  <h2>{{ currentyear }}</h2>
  {% capture year %}{{currentyear}}{% endcapture %} 
  {% endif %}
  * {{ post.date | date: "%b %d" date_to_string }} &raquo; [{{ post.title }}]({{ post.url }})
  {% endfor %}