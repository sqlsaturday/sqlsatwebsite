---
layout: home
title: "SQLSaturday Archive"
---
Welcome to the SQLSaturday archive. This is a site that holds the historical record of completed events. Current events are listed at [SQLSaturday.com](https://www.sqlsaturday.com).

If you want to know more about events from an organizer, speaker, sponsor, or attendee standpoint, sign up for our [mailing list](http://eepurl.com/hwVBKn)

## <a name="events"></a>Events

These are the SQLSaturday events that are currently scheduled. If you would like to organize or schedule an event, please visit our [running a new event](http://beta.sqlsaturday.com/newevent/) page.

<table cellspacing=0 class="table table-hover table-borderless table-sortable mt-3" width="100%">
  <thead>
        <tr>
          <th scope="col"></th>
          <th scope="col">Event Name</th>
          <th scope="col">Date</th>
        </tr>
      </thead>
      <tbody>
  {% assign TodayDate = site.time | date: '%s' %}
  {% assign count = 1 %}
  {% for post in site.posts reversed %}
    {% assign EventDate = post.date | date: '%s' %}
    {% if post.testevent != 1 %}
      {% if EventDate >= TodayDate %}
        {% assign future = 1 %}
        <tr>
          <td><img src="{{ post.thumb }}"></td>
          <td><a href="{{ post.url | absolute_url }}">{{ post.title }}</a>
          </td>
          <td>{{post.date | date: "%b %d %Y" }}</td>
        </tr>
      {% endif %}
   {% endif %}
   {% assign count = count + 1 %}
  {% endfor %}
  </tbody>
</table>

You can see completed events on the [Past Events](past) page.

