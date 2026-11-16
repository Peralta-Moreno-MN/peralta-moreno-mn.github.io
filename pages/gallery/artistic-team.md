---
layout: page
title: Artistic team
permalink: /gallery/artistic-team/
# cover_image: /assets/img/covers/artistic-team.jpg
---

<p class="gallery-breadcrumb"><a href="{{ '/gallery/' | relative_url }}">&larr; Gallery</a></p>

The illustrations on this website — backgrounds, section covers and more — were made by
these wonderful artists. Go check out their work!

<div class="illustrators">
{%- for artist in site.data.illustrators -%}
  {%- assign photo = nil -%}
  {%- for f in site.static_files -%}
    {%- if f.path == artist.photo -%}{%- assign photo = f.path -%}{%- endif -%}
  {%- endfor -%}
  <div class="illustrator-card">
    {%- if photo -%}
    <img class="illustrator-photo" src="{{ photo | relative_url }}" alt="{{ artist.name | escape }}" loading="lazy">
    {%- endif -%}
    <div>
      <h3 class="illustrator-name">{{ artist.name }}</h3>
      {%- if artist.role %}<p class="illustrator-role">{{ artist.role }}</p>{% endif -%}
      {%- if artist.bio %}<p>{{ artist.bio }}</p>{% endif -%}
      {%- if artist.instagram -%}
      <a class="illustrator-link" href="{{ artist.instagram }}" target="_blank" rel="noopener">
        <i class="fab fa-instagram"></i> Instagram
      </a>
      {%- endif -%}
      {%- if artist.email -%}
      {%- assign parts = artist.email | split: "@" -%}
      <a class="illustrator-link illustrator-email" href="#" data-u="{{ parts[0] }}" data-d="{{ parts[1] }}">
        <i class="fas fa-envelope"></i> Email
      </a>
      {%- endif -%}
    </div>
  </div>
{%- endfor -%}
</div>

<script>
  // Email addresses are assembled here so spam bots can't read them from the page source.
  document.querySelectorAll(".illustrator-email").forEach(function (a) {
    a.href = "mailto:" + a.dataset.u + "@" + a.dataset.d;
  });
</script>
