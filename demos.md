---
layout: page
title: Demos
permalink: /demos/
---

Short write-ups and video walkthroughs of my projects and papers.

{% assign items = site.demos | sort: "date" | reverse %}
{% for demo in items %}
<div class="demo-card">
  <h3><a href="{{ demo.url | relative_url }}">{{ demo.title }}</a></h3>
  <p class="demo-meta">
    {% if demo.date %}<span>{{ demo.date | date: "%b %Y" }}</span>{% endif %}
    {% if demo.venue %}<span>·</span><span>{{ demo.venue }}</span>{% endif %}
  </p>
  {% if demo.summary %}<p>{{ demo.summary }}</p>{% endif %}
  {% if demo.tags %}<p>{% for tag in demo.tags %}<span class="badge">{{ tag }}</span>{% endfor %}</p>{% endif %}
  <a href="{{ demo.url | relative_url }}">Read &amp; watch →</a>
</div>
{% endfor %}

{% if site.demos.size == 0 %}
*No demos published yet — check back soon.*
{% endif %}
