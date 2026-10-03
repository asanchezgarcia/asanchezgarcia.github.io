---
layout: page
permalink: /teaching/
title: teaching
description: Courses, workshops and supervision.
nav: true
nav_order: 3
---

<div class="teaching-hero">
  <img src="{{ '/assets/img/teaching/presenting.jpg' | relative_url }}" alt="Álvaro Sánchez-García presenting his research" loading="lazy">
  <img src="{{ '/assets/img/teaching/classroom.jpg' | relative_url }}" alt="Classroom with course slides projected" loading="lazy">
</div>

## 🎓 Teaching

{% for inst in site.data.teaching %}
<h4 class="teaching-institution">{% if inst.url %}<a href="{{ inst.url }}">{{ inst.institution }}</a>{% else %}{{ inst.institution }}{% endif %}</h4>
<ul class="teaching-list">
  {% for c in inst.courses %}
  <li>
    <span class="teaching-year">{{ c.year }}</span>
    <span class="teaching-body"><strong>{{ c.name }}</strong><br><span class="teaching-meta">{{ c.programme }} · {{ c.language }}</span></span>
  </li>
  {% endfor %}
</ul>
{% endfor %}

## 🧑‍💻 Courses

{% for course in site.data.courses %}
<div class="course-card">
  <div class="course-gallery">
    {% for img in course.images %}
    <img src="{{ img | prepend: '/assets/img/courses/' | relative_url }}" alt="{{ course.title }} – slide {{ forloop.index }}" loading="lazy">
    {% endfor %}
  </div>
  <div class="course-body">
    <h4>{{ course.title }}</h4>
    <p class="teaching-meta">{{ course.where }} · {{ course.year }} · {{ course.language }}</p>
    <p>{{ course.description }}</p>
    <div class="course-links">
      {% for l in course.links %}
      <a class="btn btn-sm z-depth-0" href="{{ l.url }}" target="_blank" rel="noopener">{{ l.emoji }} {{ l.label }}</a>
      {% endfor %}
    </div>
  </div>
</div>
{% endfor %}

{% if site.data.supervision and site.data.supervision.size > 0 %}
## 📝 Master's thesis supervision

<ul class="teaching-list">
  {% for s in site.data.supervision %}
  <li>
    <span class="teaching-year">{{ s.year }}</span>
    <span class="teaching-body"><strong>{% if s.url %}<a href="{{ s.url }}">{{ s.title }}</a>{% else %}{{ s.title }}{% endif %}</strong><br><span class="teaching-meta">{{ s.student }} · {{ s.programme }}{% if s.institution %}, {{ s.institution }}{% endif %}</span></span>
  </li>
  {% endfor %}
</ul>
{% endif %}
