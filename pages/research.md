---
layout: page
title: Research
permalink: /research/
# background_image: /assets/img/covers/research.jpg
---

<!-- ✏️ A short overview of your research: the big question and why it matters. -->

My work lies in theoretical and computational chemistry: using theory and simulations to
understand how molecules behave, and to help find the ones that could become medicines.

## Projects

<div class="home-cards">
{%- for p in site.data.projects -%}
  <a class="home-card nav-{{ p.accent | default: 'research' }}" href="{{ p.url | relative_url }}">
    <strong>{{ p.title }}</strong>
    <span>{{ p.tagline }}</span>
    {%- if p.status %}<span class="project-status">{{ p.status }}</span>{% endif -%}
  </a>
{%- endfor -%}
</div>
