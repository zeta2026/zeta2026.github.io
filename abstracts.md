---
layout: splash
title: Abstracts
permalink: /abstracts/
---

{% assign all_talks = site.talks | sort: "sort_key" %}

{% for t in all_talks %}
### {{ t.title }}

**{{ t.speaker }}**{% if t.affiliation %}, {{ t.affiliation }}{% endif %}

{{ t.abstract | markdownify }}

---

{% endfor %}
