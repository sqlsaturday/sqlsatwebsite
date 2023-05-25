---
layout: page
title: Past Events
permalink: /past/
---

The data listed here is from the public historical XML records used for the Guidebook site. If you have any corrections, please feel free to submit a Pull Request or contact the webmaster with the details.

## Previous SQLSaturday Events

<ul>
  {% assign TodayDate = site.time | date: '%s' %}
  {% for post in site.posts%}
  {% assign EventDate = post.date | date: '%s' %}
  {% if EventDate < TodayDate %}
    {% if post.testevent != 1 < TodayDate %}
    <li>
        <a href="{{ post.url | absolute_url }}">{{ post.title }}</a> -
        {% if post.postponed == 1 %}
          <b>Postponed</b>
        {% else %}
          {{post.date | date_to_long_string }}
        {% endif %}
      </li>
    {% endif %}
  {% endif %}
  {% endfor %}
  </ul>