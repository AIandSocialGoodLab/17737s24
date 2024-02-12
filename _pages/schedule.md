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
    <p style="color: red;">All deadlines are <strong style="color: red;">10:00 pm ET</strong> on the <strong style="color: red;">day indicated in the same row</strong>.</p>
    Last updated: Feb 12, 2024<br>
    Note: HW2 due date extended to <strong>Feb 18, 2024</strong>
    {% for lecture in site.data.lectures %}
      <tr>
        <th scope="row">{{ forloop.index }}</th>
        <td>{{ lecture.date }}</td>
        <td><span style="white-space: pre-wrap;">{{ lecture.topic }}</span></td>
        <td>
          {% for slide in lecture.slides %}
                      
            {% if slide.url contains "http" %}
                <a href="{{ slide.url }}">{{ slide.title }}</a>
            {% else %}
                <a href="../assets/slides/{{ slide.url }}">Slides: {{ slide.title }}</a>
            {% endif %}
            
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
