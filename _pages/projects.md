---
layout: page
title: projects
permalink: /projects/
description: a collection of my research projects
---

{% for project in site.projects reversed %}

{% if project.redirect %}
<div class="project">
    <div class="thumbnail">
        <a href="{{ project.redirect }}" target="_blank">
        {% if project.img %}
        <img class="thumbnail" src="{{ project.img | prepend: site.baseurl | prepend: site.url }}"/>
        {% else %}
        <div class="thumbnail blankbox"></div>
        {% endif %}    
        <span>
            <p>{{ project.description }}</p>
        </span>
        </a>
    </div>
    <span class="caption">
      {{project.title}}
    </span>
</div>
{% else %}

<div class="project">
    <div class="thumbnail">
        <a href="{{ project.url | prepend: site.baseurl | prepend: site.url }}">
        {% if project.img %}
        <img class="thumbnail" src="{{ project.img | prepend: site.baseurl | prepend: site.url }}"/>
        {% else %}
        <div class="thumbnail blankbox"></div>
        {% endif %}    
        <span>
            <p>{{ project.description }}</p>
        </span>
        </a>
    </div>
    <span class="caption">
      {{ project.title }}
    </span>
</div>

{% endif %}

{% endfor %}
