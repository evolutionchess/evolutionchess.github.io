---
layout: page
title: All Heroes
menu: Heroes
---
{% assign hero_pages = site.pages | where: "layout", "hero" %}
{% assign specs = hero_pages | map: "spec" | uniq | sort %}
{% assign classes = hero_pages | map: "class" | uniq | sort %}
<div id="heroes">
    <style scoped>
        #heroes {
            width: 100%;
            overflow-x: auto;
            border: 1px solid #c9c9c9;
        }
        #heroes table {
            margin-bottom: 0px;
            font-size: 14px;
        }
        @media screen and (min-width:992px) {
            #heroes {
                overflow: hidden;
                border: none;
                width: 150%;
                margin-left: -25%;
            }
            #heroes table {
                width: 100%;
                table-layout: fixed;
            }
        }
    </style>
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
                            <a href="{{page.url}}">{{page.title}}</a><br>
                        {% endif %}
                        {% endfor %}
                    </td>
                    {% endfor %}
                </tr>
            {% endfor %}
        </tbody>
    </table>
</div>