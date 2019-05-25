---
layout: page
title: All Classes
menu: Class
description: "Vanguard, Longshot, Siegebreaker, Guardian, Specialist, Supporter, Blaster, Summoner, Assassin. Read more about all AOE Classes (Roles), tips and guide about how to use them wisely!"
---
{% assign hero_pages = site.pages | where: "layout", "hero" %}
{% assign classes = site.data.classes | map: "Name" | uniq %}
{% for class in classes %}
<h2 id="{{ class | replace: " ", "-" }}">{{ class }}</h2>
<div class="heroes">
    {% for page in hero_pages %}
        {% if page.class contains class %}
            <a href="{{page.url}}" title="{{page.title}}">
                <img src="/assets/img/heroes/avatar/{{page.title}}.png"/>
            </a>
        {% endif %}
    {% endfor %}
</div>
#### Active when you control (N) {{ class }} on the field:
{% assign levels = site.data.classes | where: "Name", class %}
{% for level in levels %}
<div>({{ level.Require }}) {{ level.Buff }}</div>
{% endfor %}
{% endfor %}