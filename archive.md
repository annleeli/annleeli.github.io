---
layout: page
title: Archive
published: true
---

<!--## Blog Posts

{% for post in site.posts %}
  * {{ post.date | date_to_string }} &raquo; [ {{ post.title }} ]({{ post.url }})
{% endfor %}-->

{% for post in site.posts %}
  {% capture currentyear %}{{post.date | date: "%B %Y"}}{% endcapture %}
  {% if currentyear != year %}
    {% unless forloop.first %}</ul>{% endunless %}
    <h1>{{ currentyear }}</h1>
    <ul>
    {% capture year %}{{currentyear}}{% endcapture %} 
  {% endif %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% if forloop.last %}</ul>{% endif %}
{% endfor %}
