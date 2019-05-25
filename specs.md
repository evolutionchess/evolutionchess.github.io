---
layout: page
title: All Specs
menu: Spec
description: "Beast, Walker, Puppet, Raptor, Immortal, Mech, Panda, Psyker, Marine, Air Force, Kraken, Insectoid, Rider. Read more about all AOE Spec (Race), tips and guide about how to use them wisely!"
---
{% assign hero_pages = site.pages | where: "layout", "hero" %}
{% assign specs = site.data.specs | map: "Name" | uniq %}
{% for spec in specs %}
<h2 id="{{ spec | replace: " ", "-" }}">{{ spec }}</h2>
<div class="heroes">
    {% for page in hero_pages %}
        {% if page.spec contains spec %}
            <a href="{{page.url}}" title="{{page.title}}">
                <img src="/assets/img/heroes/avatar/{{page.title}}.png"/>
            </a>
        {% endif %}
    {% endfor %}
</div>
#### Active when you control (N) {{ spec }} on the field:
{% assign levels = site.data.specs | where: "Name", spec %}
{% for level in levels %}
<div>({{ level.Require }}) {{ level.Buff }}</div>
{% endfor %}
{% endfor %}