---
layout: page
title: "Research Work"
permalink: /Research Work/
main_nav: true
---

{% for category in site.categories %}
  {% capture platform studies %}{{ category | first }}{% endcapture %}
  <h2 id="{{paltform}}">{{platform }}</h2>
  {% for desc in site.descriptions %}
    {% if desc.paltform == cat %}
      <p class="desc"><em>{{ desc.desc }}</em></p>
    {% endif %}
  {% endfor %}
  <ul class="posts-list">
  {% for post in site.categories[cat] %}
    <li>
      <strong>
        <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </strong>
      <span class="post-date">- {{ post.date | date_to_long_string }}</span>
    </li>
  {% endfor %}
  </ul>
  {% if forloop.last == false %}<hr>{% endif %}
{% endfor %}
<br>
