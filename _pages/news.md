---
layout: page
title: News
permalink: /news/
nav: true
---

<div class="news">
    <div class="table-responsive">
      <table class="table table-sm table-borderless">
        {% assign news = site.news | sort: 'date' | reverse %}
        {% for item in news %}
          <tr>
            <th scope="row">{{ item.date | date: "%b, %Y" }}</th>
            <td  style="height:40px;width:750px">
              {% if item.inline %}
                {{ item.content | markdownify | replace: '<p>', '' | replace: '</p>', '' | emojify }}
              {% else %}
                <a class="news-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
              {% endif %}
            </td>
          </tr>
        {% endfor %}
      </table>
    </div>
</div>
