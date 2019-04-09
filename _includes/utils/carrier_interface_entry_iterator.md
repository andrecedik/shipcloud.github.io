<ul>
{% for entry in include.entries %}
  <li>{{ entry.name }} ({{ entry.key }})</li>
{% endfor %}
</ul>
