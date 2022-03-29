---
layout: splash
title: "Publications"
permalink: /publication/
author_profile: false
---

{% include base_path %}

{% for post in site.publications reversed %}
  {% include publication-row.html %}
{% endfor %}