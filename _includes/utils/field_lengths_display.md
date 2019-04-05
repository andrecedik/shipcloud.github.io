{% assign carrier_specific_field_lengths=site.shipcloud.supported_carriers.carrier_features[include.carrier_name][include.carrier_interface].field_lengths %}
<ul>
{% for field_length_entries in carrier_specific_field_lengths %}
  <li>
    {% for field_length_entry_lev1 in field_length_entries %}
        {% assign second_level_size = field_length_entry_lev1[1] | size %}
        {% if second_level_size > 1 %}
            {{ field_length_entry_lev1[0] }}: {{ field_length_entry_lev1[1] }}
        {% elsif second_level_size == 1%}
            {{ field_length_entry_lev1[0] }}
            <ul>
                {% for field_length_entry_lev2 in field_length_entry_lev1[1] %}
                    {% if field_length_entry_lev2[1] %}
                    <li>{{ field_length_entry_lev2[0] }}: {{ field_length_entry_lev2[1] }}</li>
                    {% else %}
                    <li>{{ field_length_entry_lev2[0] }}</li>
                    {% endif %}
                {% endfor %}
            </ul>
        {% endif %}
    {% endfor %}
  </li>
{% endfor %}
</ul>
