---
layout: reports
permalink: /reports/
title: Completed Student Projects
description: Student projects upon completion of our program.
---

{% for project in site.data.reports %}

<tr>
    <td align="left">{{ forloop.index }}</td>
    <td align="left">
    <strong>{{ project.title }}</strong><br/>
    {% for author in project.authors %}
    {%   if author.url %}
    <a href="{{author.url}}">{{author.name}}</a>{% unless forloop.last %},{% endunless %}
    {%   else %}
    {{author.name}}{% unless forloop.last %},{% endunless %}
    {%   endif %}
    {% endfor %}
    </td>
    <td align="left"><a href="{{ project.path | relative_url }}">report</a></td>
</tr>

{% endfor %}
