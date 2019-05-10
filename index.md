---
layout: home
title: Arena Of Evolution - Red Tides Strategy Guide
---
<h2>Wiki</h2>
<div class="row">
    <div class="col-12 col-md-4">
        <a href="/heroes.html" class="btn btn-feature">Heroes</a>
    </div>
    <div class="col-6 col-md-4">
        <a href="/specs.html" class="btn btn-feature">Specs</a>
    </div>
    <div class="col-6 col-md-4">
        <a href="/classes.html" class="btn btn-feature">Classes</a>
    </div>
</div>
{%- if site.posts.size > 0 -%}
<h2>Guides</h2>
<ul class="post-list">
    {%- for post in site.posts -%}
    <li>
    {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
    <span class="post-meta">{{ post.date | date: date_format }}</span>
    <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">
        {{ post.title | escape }}
        </a>
    </h3>
    {%- if site.show_excerpts -%}
        {{ post.excerpt }}
    {%- endif -%}
    </li>
    {%- endfor -%}
</ul>

<p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | relative_url }}">via RSS</a></p>
{%- endif -%}
