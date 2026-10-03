---
layout: page
permalink: /data/
title: data
description: Open datasets I have built or contributed to. Click on a card to access the data.
nav: true
nav_order: 4
---

<div class="data-grid">
  {% for d in site.data.datasets %}
  <article class="data-card">
    <a class="data-image" href="{{ d.url }}" target="_blank" rel="noopener" aria-label="Open {{ d.title }}">
      <img src="{{ d.image | prepend: '/assets/img/data/' | relative_url }}" alt="" loading="lazy">
      <span class="data-repo">🗄️ {{ d.repository }}</span>
    </a>
    <div class="data-body">
      <h3><a href="{{ d.url }}" target="_blank" rel="noopener">{{ d.title }}</a></h3>
      {% if d.subtitle %}<p class="data-subtitle">{{ d.subtitle }}</p>{% endif %}
      <div class="data-tags">
        {% if d.year %}<span>{{ d.year }}</span>{% endif %}
        {% for t in d.tags %}<span>{{ t }}</span>{% endfor %}
      </div>
      <p>{{ d.summary }}</p>
      {% if d.description %}
      <details class="data-more">
        <summary>More</summary>
        <p>{{ d.description }}</p>
      </details>
      {% endif %}
      {% if d.citation %}
      <details class="data-more">
        <summary>How to cite</summary>
        <p class="data-citation">{{ d.citation }}</p>
        <button class="btn btn-sm z-depth-0 data-copy" type="button">📋 Copy citation</button>
      </details>
      {% endif %}
      <div class="data-links">
        <a class="btn btn-sm z-depth-0" href="{{ d.url }}" target="_blank" rel="noopener">🔗 Access the data</a>
      </div>
    </div>
  </article>
  {% endfor %}
</div>

<script>
  document.querySelectorAll(".data-copy").forEach(function (btn) {
    btn.addEventListener("click", function () {
      var text = btn.parentElement.querySelector(".data-citation").innerText.trim();
      navigator.clipboard.writeText(text).then(function () {
        var old = btn.textContent;
        btn.textContent = "✅ Copied";
        setTimeout(function () { btn.textContent = old; }, 1500);
      });
    });
  });
</script>
