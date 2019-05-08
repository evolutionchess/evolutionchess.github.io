---
layout: page
title: All minions
menu: Minions
---
Minions
<ul>
    {% for page in site.pages %}
        {% if page.layout == "minion" %}
            <li><a href="{{page.url}}">{{page.title}}</a></li>
        {% endif %}
    {% endfor %}
</ul>