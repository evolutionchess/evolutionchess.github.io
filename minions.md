---
layout: page
title: All minions
menu: Minions
---
{% assign minion_pages = site.pages | where: "layout", "minion" %}
{% assign all_specs = minion_pages | map: "spec" %}
{% assign specs = all_specs | uniq %}
{% for spec in specs %}
<h3>{{spec}}</h3>
<ul>
    {% for page in minion_pages %}
        {% if page.spec == spec %}
            <li><a href="{{page.url}}">{{page.title}}</a></li>
        {% endif %}
    {% endfor %}
</ul>
{% endfor %}