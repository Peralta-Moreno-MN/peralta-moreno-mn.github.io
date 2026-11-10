---
layout: page
title: Open positions
permalink: /open-positions/
# cover_image: /assets/img/covers/open-positions.jpg
---

**There are no positions currently available.**

If you are interested in a possible collaboration, feel free to
[get in touch]({{ '/about/#contact' | relative_url }})!

## But hey! 👋

If you're looking for someone in the field, check out these cool people.
They do amazing science and might be looking for someone like you:

{% assign groups = site.data.people | group_by: "type" %}
{% for group in groups %}
### {{ group.name }}

<ul class="people-list">
{%- for person in group.items -%}
  <li>
    <a href="{{ person.link }}"><strong>{{ person.name }}</strong></a>
    {%- if person.affiliation %} · {{ person.affiliation }}{% endif -%}
    {%- if person.topic %}<br><small>{{ person.topic }}</small>{% endif -%}
  </li>
{%- endfor -%}
</ul>
{% endfor %}
