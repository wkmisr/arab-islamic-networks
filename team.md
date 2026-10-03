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
  <div class="person-text">{{ t.lead.text | markdownify }}</div>
  {% include person-links.html p=t.lead %}
</div>

## Co-investigators

{% for m in t.members %}
<div class="person">
  <p class="person-name">{{ m.name }}</p>
  {% if m.affiliation != "" %}<p class="person-aff">{{ m.affiliation }}</p>{% endif %}
  {% if m.text != "" %}<div class="person-text">{{ m.text | markdownify }}</div>{% endif %}
  {% include person-links.html p=m %}
</div>
{% endfor %}

## Research collaborators

{% for a in t.associates %}
<div class="person">
  <p class="person-name">{{ a.name }}</p>
  {% if a.affiliation != "" %}<p class="person-aff">{{ a.affiliation }}</p>{% endif %}
  {% if a.text != "" %}<div class="person-text">{{ a.text | markdownify }}</div>{% endif %}
  {% include person-links.html p=a %}
</div>
{% endfor %}

{% if t.show_collaborators %}
## International collaborators

{% for c in t.collaborators %}
<div class="person">
  <p class="person-name">{{ c.name }}</p>
  <p class="person-aff">{{ c.affiliation }}</p>
  <div class="person-text">{{ c.text | markdownify }}</div>
  {% include person-links.html p=c %}
</div>
{% endfor %}
{% endif %}
