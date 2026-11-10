---
layout: page
title: Contact
permalink: /contact/
# background_image: /assets/img/covers/contact.jpg
---

Feel free to reach out for collaborations, questions about the tutorials, or just to say hi!

<p class="contact-email">
  <a class="contact-button" id="contact-email" href="#" data-u="peralta.mnuria" data-d="gmail.com">
    <i class="fas fa-envelope"></i> <span>Send me an email</span>
  </a>
  <noscript><br>peralta.mnuria [at] gmail [dot] com</noscript>
</p>

<script>
  // The address is assembled here so spam bots can't read it from the page source.
  (function () {
    var a = document.getElementById("contact-email");
    var addr = a.dataset.u + "@" + a.dataset.d;
    a.href = "mailto:" + addr;
    a.querySelector("span").textContent = addr;
  })();
</script>

## Elsewhere

<ul class="contact-links">
{%- for s in site.data.social -%}
  {%- unless s.url == "/contact/" %}
  <li><a href="{{ s.url }}" target="_blank" rel="noopener"><i class="{{ s.icon }} fa-fw"></i> {{ s.title }}</a></li>
  {%- endunless -%}
{%- endfor %}
</ul>
