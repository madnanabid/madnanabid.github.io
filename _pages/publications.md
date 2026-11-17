---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% assign publications_by_year = site.publications | group_by_exp: "post", "post.date | date: '%Y'" | sort: "name" | reverse %}

{% for year in publications_by_year %}
  <h2>{{ year.name }}</h2>

  {% assign year_publications = year.items | sort: "date" | reverse %}

  {% for post in year_publications %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}
