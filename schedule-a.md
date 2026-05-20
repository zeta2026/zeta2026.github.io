---
layout: splash
title: Draft schedule
permalink: /schedule-a/
---

All talks will place in room **AC201** (University of Galway, Arts & Science
Concourse)
([Google Maps](https://maps.app.goo.gl/5PH9HdYRoqzZCWyr5), [campus map](https://www.universityofgalway.ie/media/mindfulway/files/Map-showing-room-AC201.pdf)).

{% assign days = site.data.schedule-a.days %}
{% for day in days %}
## {{ day.label }}

<ul>
{% for s in day.sessions %}
  <li>
    {{ s.time }} — 
    {% if s.talk_ref %}
    {% assign t = site.talks | where: "slug", s.talk_ref | first %}
      {% if t and t.abstract %}
      {{ t.speaker }}: {{ t.title }}
      <details style="display:inline;">
        <summary style="display:inline; cursor:pointer; color:#3366cc; margin-left:0.5em;">
          (abstract)
        </summary>
        <div style="margin-top:0.5em;">
          {{ t.abstract | markdownify }}
        </div>
      </details>
      {% endif %}
    {% else %}
    {% if s.speaker %}{{ s.speaker }}: {% endif %}{{ s.title }}{% if s.room %} ({{ s.room }}){% endif %}
    {% endif %}
  </li>
{% endfor %}
</ul>
{% endfor %}
