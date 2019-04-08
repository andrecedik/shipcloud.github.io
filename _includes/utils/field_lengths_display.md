{% assign carrier_specific_field_lengths=site.data.carriers[include.carrier_name].interfaces[include.carrier_interface].implementations.shipcloud.field_lengths %}
<ul>
{% for entries_lev1 in carrier_specific_field_lengths %}
  <li>
    {% if entries_lev1[1].first %}
        {{ entries_lev1[0] }}
        <ul>
            {% for entries_lev2 in entries_lev1[1] %}
                <li>
                    {% if entries_lev2[1].first %}
                        {{ entries_lev2[0] }}
                        <ul>
                        {% for entries_lev3 in entries_lev2[1] %}
                            <li>
                                {{ entries_lev3[0] }}: {{ entries_lev3[1] }}
                            </li>
                        {% endfor %}
                        </ul>
                    {% else %}
                        {{ entries_lev2[0] }}: {{ entries_lev2[1] }}
                    {% endif %}
                </li>
            {% endfor %}
        </ul>
    {% else %}
        {{ entries_lev1[0] }}: {{ entries_lev1[1] }}
    {% endif %}
  </li>
{% endfor %}
</ul>
