---
title: Tom testing CSV
---


Testing loading data from CSV file

{% assign row = site.data.test[0] %}
{{ row | inspect }}

<ul>
{% for member in site.data.test %}
  <li>
    <a href="https://github.com/{{ member.github }}">
      {{ member.name }}
    </a>
  </li>
{% endfor %}
</ul>


<table>
  {% for row in site.data.test %}
    {% if forloop.first %}
    <tr>
      {% for pair in row %}
        <th>{{ pair[0] }}</th>
      {% endfor %}
    </tr>
    {% endif %}
  {% endfor %}
</table>


<table>
  {% for row in site.data.test %}
    {% if forloop.first %}
    <tr>
      {% for pair in row %}
        <th>{{ pair[0] }}</th>
      {% endfor %}
    </tr>
    {% endif %}

    {% tablerow pair in row %}
      {{ pair[1] }}
    {% endtablerow %}
  {% endfor %}
</table>