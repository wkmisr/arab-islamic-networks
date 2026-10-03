---
layout: page
title: Team
permalink: /team/
---
{% assign t = site.data.team %}
## Principal investigator

<div class="person">
  <p class="person-name">{{ t.lead.name }}</p>
  <p class="person-aff">{{ t.lead.affiliation }}</p>
  <p class="person-text">{{ t.lead.text }}</p>
</div>

## Co-investigators

{% for m in t.members %}
<div class="person">
  <p class="person-name">{{ m.name }}</p>
  {% if m.affiliation != "" %}<p class="person-aff">{{ m.affiliation }}</p>{% endif %}
  {% if m.text != "" %}<p class="person-text">{{ m.text }}</p>{% endif %}
</div>
{% endfor %}

## Research collaborators

{% for a in t.associates %}
<div class="person">
  <p class="person-name">{{ a.name }}</p>
  {% if a.affiliation != "" %}<p class="person-aff">{{ a.affiliation }}</p>{% endif %}
  {% if a.text != "" %}<p class="person-text">{{ a.text }}</p>{% endif %}
</div>
{% endfor %}

{% if t.show_collaborators %}
## International collaborators

{% for c in t.collaborators %}
<div class="person">
  <p class="person-name">{{ c.name }}</p>
  <p class="person-aff">{{ c.affiliation }}</p>
  <p class="person-text">{{ c.text }}</p>
</div>
{% endfor %}
{% endif %}
