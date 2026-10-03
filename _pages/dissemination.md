---
layout: page
title: dissemination
permalink: /dissemination/
description: Op-eds, reports and other work for a non-academic audience.
---

{% assign d = site.data.dissemination %}

<h2 class="media-section">✍️ Op-eds</h2>
{% include media_list.liquid items=d.op_eds %}

<h2 class="media-section">📑 Reports &amp; other</h2>

<div class="reports">
  {% assign reports = d.reports | sort: 'year' | reverse %}
  {% for r in reports %}
  <div class="report">
    <div class="report-year">{{ r.year }}</div>
    <div class="report-body">
      <div class="title">{% if r.url %}<a href="{{ r.url }}" target="_blank" rel="noopener">{{ r.title }}</a>{% else %}{{ r.title }}{% endif %}</div>
      <div class="author">{{ r.author | replace: 'Sánchez-García, Á.', '<em class="me">Sánchez-García, Á.</em>' }}</div>
      <div class="periodical"><em>{{ r.publisher }}</em>{% if r.pages %}, pp. {{ r.pages }}{% endif %}{% if r.isbn %} · ISBN {{ r.isbn }}{% endif %}</div>
      <div class="links">
        {% if r.url %}<a class="btn btn-sm z-depth-0" href="{{ r.url }}" target="_blank" rel="noopener">🔗 Read</a>{% endif %}
        {% if r.press %}<a class="btn btn-sm z-depth-0 report-press-btn" role="button">📰 Press ({{ r.press.size }})</a>{% endif %}
      </div>
      {% if r.press %}
      <div class="report-press">
        <ul class="media-list">
          {% assign rp = r.press | sort: 'date' | reverse %}
          {% for e in rp %}
          <li>
            <span class="media-date">{{ e.date | date: '%d/%m/%Y' }}</span>
            <span class="media-body"><span class="media-outlet">{{ e.outlet }}</span><a href="{{ e.url }}" target="_blank" rel="noopener">{{ e.title }}</a>{% if e.author %} <span class="media-meta">— {{ e.author }}</span>{% endif %}</span>
          </li>
          {% endfor %}
        </ul>
      </div>
      {% endif %}
    </div>
  </div>
  {% endfor %}
</div>

<script>
  document.querySelectorAll(".report-press-btn").forEach(function (btn) {
    btn.addEventListener("click", function () {
      btn.closest(".report-body").querySelector(".report-press").classList.toggle("open");
    });
  });
</script>
