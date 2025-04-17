---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

<!-- {% if site.author.googlescholar %}
  <div class="wordwrap">You can also find my articles on <a href="{{site.author.googlescholar}}">my Google Scholar profile</a>.</div>
{% endif %} -->

{% include base_path %}


{%- assign pubs_sorted_by_date = site.publications | sort: "date" | reverse -%}
{%- assign sorted_pubs = pubs_sorted_by_date | sort: "weight" -%}

{% for post in sorted_pubs %}
  {% include archive-single.html %}
{% endfor %}