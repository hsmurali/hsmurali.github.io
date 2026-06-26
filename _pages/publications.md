---
layout: page
permalink: /publications/
title: Publications
description: <sup>*</sup> Authors contributed equally.
years: [2026, 2025, 2024, 2023, 2021, 2019]
nav: true
---

<div class="publications" id="publications-by-year">

{% for y in page.years %}
  <div class="publication-year">
    <h4 class="year">
      <button class="btn btn-link year-toggle{% unless forloop.first %} collapsed{% endunless %}" type="button" data-toggle="collapse" data-target="#year-{{ y }}" aria-expanded="{% if forloop.first %}true{% else %}false{% endif %}" aria-controls="year-{{ y }}">
        {{ y }}
      </button>
    </h4>
    <div id="year-{{ y }}" class="year-collapse collapse{% if forloop.first %} show{% endif %}">
      {% bibliography -f papers -q @*[year={{y}}]* %}
    </div>
  </div>
{% endfor %}

</div>
