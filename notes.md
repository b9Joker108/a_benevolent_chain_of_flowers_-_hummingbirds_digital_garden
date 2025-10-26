---
layout: default
title: Notes
---

# 📝 Notes

More developed ideas and learning notes. These concepts have been tended to and are actively growing.

<div class="garden-grid">
{% for note in site.notes %}
  <a href="{{ note.url | relative_url }}" class="garden-card">
    <h3>{{ note.title }}</h3>
    {% if note.date %}
    <p class="date">{{ note.date | date: "%B %d, %Y" }}</p>
    {% endif %}
    {% if note.excerpt %}
    <p>{{ note.excerpt | strip_html | truncatewords: 30 }}</p>
    {% endif %}
  </a>
{% endfor %}
</div>

---

Notes are more established pieces of knowledge—refined through reading, thinking, and experience. They're still evolving, but they have a clearer structure and purpose.
