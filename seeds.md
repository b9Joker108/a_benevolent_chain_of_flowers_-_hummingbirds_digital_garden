---
layout: default
title: Seeds
---

# 🌱 Seeds

Fresh ideas and early-stage thoughts. These are concepts just beginning to sprout—raw, unpolished, and full of potential.

<div class="garden-grid">
{% for seed in site.seeds %}
  <a href="{{ seed.url | relative_url }}" class="garden-card">
    <h3>{{ seed.title }}</h3>
    {% if seed.date %}
    <p class="date">{{ seed.date | date: "%B %d, %Y" }}</p>
    {% endif %}
    {% if seed.excerpt %}
    <p>{{ seed.excerpt | strip_html | truncatewords: 30 }}</p>
    {% endif %}
  </a>
{% endfor %}
</div>

---

Seeds represent the beginning of an idea—they may be incomplete, speculative, or exploratory. Over time, with care and attention, they may grow into more developed notes.
