---
layout: default
title: Thoughts
---

# 💭 Thoughts

Reflections, musings, and personal insights. The blooming flowers of the garden.

<div class="garden-grid">
{% for thought in site.thoughts %}
  <a href="{{ thought.url | relative_url }}" class="garden-card">
    <h3>{{ thought.title }}</h3>
    {% if thought.date %}
    <p class="date">{{ thought.date | date: "%B %d, %Y" }}</p>
    {% endif %}
    {% if thought.excerpt %}
    <p>{{ thought.excerpt | strip_html | truncatewords: 30 }}</p>
    {% endif %}
  </a>
{% endfor %}
</div>

---

Thoughts are personal reflections and insights—they capture moments of understanding, questions worth pondering, and observations about life and learning.
