---
layout: page
title: Experience
permalink: /experience/
---

<h2 class="section">Research</h2>
<ul class="records">
{%- for e in site.data.experience %}
  <li class="record">
    <div class="record-head">
      <div class="record-title">
        {%- if e.url %}<a href="{{ e.url }}">{{ e.institution }}</a>{% else %}{{ e.institution }}{% endif -%}
      </div>
      {%- if e.date %}<div class="record-date">{{ e.date }}</div>{% endif -%}
    </div>
    <div class="record-sub">
      {{ e.role }}
      {%- if e.advisor %} &middot; with
        {%- if e.advisor_url %} <a href="{{ e.advisor_url }}">{{ e.advisor }}</a>
        {%- else %} {{ e.advisor }}{% endif -%}
      {% endif %}
    </div>
    {%- if e.bullets %}
    <ul class="record-bullets">
      {%- for b in e.bullets %}<li>{{ b }}</li>{% endfor %}
    </ul>
    {%- elsif e.description %}<p class="record-desc">{{ e.description }}</p>{% endif %}
  </li>
{%- endfor %}
</ul>

<h2 class="section">Education</h2>
{%- include education.html -%}
