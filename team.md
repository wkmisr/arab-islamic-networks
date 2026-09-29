---
layout: page
title: Team
permalink: /team/
---
{% assign t = site.data.team %}
## Principal investigator

**{{ t.lead.name }}**, {{ t.lead.affiliation }}. {{ t.lead.text }}

## Co-investigators

{% for m in t.members %}**{{ m.name }}**{% if m.affiliation != "" %}, {{ m.affiliation }}{% endif %}. {{ m.text }}

{% endfor %}
## Research collaborators

{% for a in t.associates %}**{{ a.name }}**, {{ a.affiliation }}.{% if a.text != "" %} {{ a.text }}{% endif %}

{% endfor %}
{% if t.show_collaborators %}
## International collaborators

{% for c in t.collaborators %}**{{ c.name }}**, {{ c.affiliation }}. {{ c.text }}

{% endfor %}
{% endif %}
Graduate students assist with data entry.
