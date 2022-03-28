---
layout: splash
title: "Publications"
permalink: /publications/
author_profile: false
---

{% include base_path %}

{% for post in site.publications reversed %}
  {% include publication-row.html %}
{% endfor %}