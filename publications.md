---
layout: page
title: Publications
permalink: /publications/
---

{%- assign pubs = site.data.publications -%}
{%- assign years = pubs | map: "year" | uniq | sort | reverse -%}
{%- for y in years %}
<h2 class="section">{{ y }}</h2>
<ul class="pub-list">
  {%- assign group = pubs | where: "year", y %}
  {%- for pub in group %}{% include publication.html pub=pub %}{% endfor %}
</ul>
{%- endfor %}
