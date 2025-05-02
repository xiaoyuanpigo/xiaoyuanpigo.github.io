---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if site.author.googlescholar %}
  <div class="wordwrap">You can also find my articles on <a href="{{site.author.googlescholar}}">my Google Scholar profile</a>.</div>
{% endif %}




{% include base_path %}

{%- assign pubs_sorted = site.publications | sort: "weight" |  -%}


{%- assign topics = pubs_sorted | map: "topic" | uniq |  -%}

{%- for topic in topics %}
<hr>
<h2 style="font-weight: bold; color: black; margin-top: 2em;">{{ topic }}</h2>

{%- assign pubs_in_topic = pubs_sorted | where: "topic", topic -%}
{%- assign pubs_sorted_by_date = pubs_in_topic | sort: "date" | reverse -%}
{%- assign sorted_pubs = pubs_sorted_by_date | sort: "weight" -%}

{%- for post in sorted_pubs %}
  {% include archive-single.html %}
{%- endfor %}
{%- endfor %}