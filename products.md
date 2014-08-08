---
layout: page
title: Products
permalink: /products/
---
<dl>
{% for page in site.pages %}
  {% if page.layout == 'product' && page.title %}
  <dt><a class="page-link" href="{{ page.url | prepend: site.baseurl }}">{{ page.title }}</a></dt>
  <dd>{{ page.summary }}</dd>
  {% endif %}
{% endfor %}
</dl>
