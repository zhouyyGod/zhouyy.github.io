---
layout: page
title: "Test"
description: "Description of Project #1"
header-img: "img/home-bg.jpg"
category: test
---

<!-- 分页 -->
<!-- Pager -->
{% if paginator.total_pages > 1 %}
<ul class="pager">
    {% if paginator.previous_page %}
    <li class="previous">
        <a href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}">&larr; previous</a>
    </li>
    {% endif %}

    <li class="page">
        {% if paginator.page == 1 %}
        <span class="current-page">1</span>
        {% else %}
        <a href="{{ site.url }}">1</a>
        {% endif %}
    </li>

    {% for count in (2..paginator.total_pages) %}
    <li class="page">
        {% if count == paginator.page %}
        <span class="current-page">{{ count }}</span>
        {% else %}
        <a href="{{ site.url }}/page{{count}}">{{ count }}</a>
        {% endif %}
    </li>
    {% endfor %}


    {% if paginator.next_page %}
    <li class="next">
        <a href="{{ paginator.next_page_path | prepend: site.baseurl | replace: '//', '/' }}">next &rarr;</a>
    </li>
    {% endif %}
</ul>
{% endif %}