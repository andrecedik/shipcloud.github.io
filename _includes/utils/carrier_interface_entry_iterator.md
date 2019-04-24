<ul>
{% for entry in include.entries %}
  <li>{{ entry.name }} ({{ entry.key }})</li>
{% endfor %}
</ul>

{% for entry in include.entries %}
  {% if include.carrier && include.type %}
    {% capture include_file %}{% include examples/carriers/{{include.carrier}}/{{include.type}}/{{entry.key}}.md %}{% endcapture %}
{{ include_file | markdownify | remove: '<p>' | remove: '</p>' }}
  {% endif %}
{% endfor %}
