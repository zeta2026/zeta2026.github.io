---
layout: splash
title: Draft schedule A
permalink: /schedule-a/
---

{% assign days = site.data.schedule-a.days %}
{% for day in days %}
## {{ day.label }}

<ul>
{% for s in day.sessions %}
  <li>
    {{ s.time }} — {% if s.speaker %}{{ s.speaker }}: {% endif %}{{ s.title }}{% if s.room %} ({{ s.room }}){% endif %}
    {% if s.talk_ref %}
      {% assign t = site.talks | where: "slug", s.talk_ref | first %}
      {% if t and t.abstract %}
      <details style="display:inline;">
        <summary style="display:inline; cursor:pointer; color:#3366cc; margin-left:0.5em;">
          (abstract)
        </summary>
        <div style="margin-top:0.5em;">
          {{ t.abstract | markdownify }}
        </div>
      </details>
      {% endif %}
    {% endif %}
  </li>
{% endfor %}
</ul>
{% endfor %}
