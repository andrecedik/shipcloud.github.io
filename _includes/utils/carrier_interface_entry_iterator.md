{% for entry in include.entries %}
  {% if page.carrier and include.type and include.carrier_interface %}
{% capture include_file %}{% include examples/carriers/{{ page.carrier }}/{{ include.carrier_interface }}/{{ include.type }}/{{ entry.key }}.md type=include.type carrier_interface=include.carrier_interface %}{% endcapture %}
{{ include_file | markdownify | remove: '<p>' | remove: '</p>' }}
  {% else %}
- {{ entry.display_name }} ({{ entry.key }})
  {% endif %}
{% endfor %}
