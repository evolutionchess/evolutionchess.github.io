---
layout: page
title: All Heroes
menu: Heroes
---
{% assign hero_pages = site.pages | where: "layout", "hero" %}
{% assign specs = hero_pages | map: "spec" | uniq | sort %}
{% assign classes = hero_pages | map: "class" | uniq | sort %}
<div id="heroes">
    <table>
        <thead>
            <tr>
                <th></th>
                {% for class in classes %}
                <th>{{class}}</th>
                {% endfor %}
            </tr>
        </thead>
        <tbody>
            {% for spec in specs %}
                <tr>
                    <th>{{spec}}</th>
                    {% for class in classes %}
                    <td>
                        {% for page in hero_pages %}
                        {% if page.spec == spec and page.class == class %}
                            <a href="{{page.url}}" title="{{page.title}}">
                            <img src="/assets/img/heroes/avatar/{{page.title}}.png"/>
                            </a>
                        {% endif %}
                        {% endfor %}
                    </td>
                    {% endfor %}
                </tr>
            {% endfor %}
        </tbody>
    </table>
</div>