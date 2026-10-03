---
layout: page
title: collaborations
permalink: /collaborations/
description: Interviews and expert commentary in the press, on the radio and on television.
---

{% assign m = site.data.media_appearances %}

<div class="media-stats">
  <a href="#press"><strong>{{ m.press.size }}</strong><span>📰 Press</span></a>
  <a href="#radio"><strong>{{ m.radio.size }}</strong><span>📻 Radio</span></a>
  <a href="#tv"><strong>{{ m.tv.size }}</strong><span>📺 TV</span></a>
</div>

<h2 id="press" class="media-section">📰 Press</h2>
{% include media_list.liquid items=m.press %}

<h2 id="radio" class="media-section">📻 Radio</h2>
{% include media_list.liquid items=m.radio %}

<h2 id="tv" class="media-section">📺 TV</h2>
{% include media_list.liquid items=m.tv %}
