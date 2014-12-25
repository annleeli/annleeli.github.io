---
layout: page
title: Archive
published: true
---

<!--## Blog Posts

{% for post in site.posts %}
  * {{ post.date | date_to_string }} &raquo; [ {{ post.title }} ]({{ post.url }})
{% endfor %} -->

{% for post in site.posts %}
  {% capture currentyear %}{{post.date | date: "%B %Y"}}{% endcapture %}
  {% if currentyear != year %}
    ##{{ currentyear }}
    * {% capture year %}{{currentyear}}{% endcapture %} 
  {% endif %}
    *[ {{ post.title }} ]({{ post.url }})
{% endfor %}