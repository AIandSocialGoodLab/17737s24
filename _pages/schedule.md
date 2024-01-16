---
layout: page
title: Schedule
permalink: /schedule/
nav: true
nav_order: 1
---
<table>
  <thead>
    <tr>
      <th>#</th>
      <th>Date</th>
      <th>Topic</th>
      <th>Slides and References</th>
      <th>Note</th>
    </tr>
  </thead>
  <tbody>
    {% for lecture in site.data.lectures %}
      <tr>
        <th scope="row">{{ lecture.number }}</th>
        <td>{{ lecture.date }}</td>
        <td><span style="white-space: pre-wrap;">{{ lecture.topic }}</span></td>
        <td>
          {% for slide in lecture.slides %}
            <a href="{{ slide.url }}">{{ slide.title }}</a>
            {% if slide.same_line %}
                    <!-- Nothing here, continue on the same line -->
            {% else %}
                <br>
            {% endif %}
          {% endfor %}
        </td>
        <td> {{ lecture.note }} </td>
      </tr>
    {% endfor %}
  </tbody>
</table>
