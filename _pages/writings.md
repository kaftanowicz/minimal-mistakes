---
layout: archive #single
title: "Writings"
lang: en
ref: writings
permalink: /writings/
author_profile: true
header:
  image: /images/header.jpg
---

Looks like I haven't written anything in English here yet. There should be more stuff on the Polish version of this page.

{% include group-by-array collection=site.posts field="categories" %}

{% for category in group_names %}
  {% assign posts = group_items[forloop.index0] | where:"lang", page.lang | where:"translated", false %}
{% unless posts.size == 0 %}
  <h1 id="{{ category | slugify }}" class="archive__subtitle">{{ category }}</h1>
  {% for post in posts %}
    		{% include archive-single.html %}
  {% endfor %}
{% endunless %}
{% endfor %}

