---
title: Hermes @ shipcloud
nav: carriers

---

# Hermes

## Profi Paketservice

### Services
{: #props-services}
<ul>
{% for service in site.shipcloud.supported_carriers.carrier_features.hermes.props.services %}
  <li>{{ service.name }} ({{ service.key }})</li>
{% endfor %}
</ul>

### Additional services
{: #props-additional-services}
<ul>
{% for additional_service in site.shipcloud.supported_carriers.carrier_features.hermes.props.additional_services %}
  <li>{{ additional_service.name }} ({{ additional_service.key }})</li>
{% endfor %}
</ul>

### Package types
{: #props-package-types}
<ul>
{% for package_type in site.shipcloud.supported_carriers.carrier_features.hermes.props.package_types %}
  <li>{{ package_type.name }} ({{ package_type.key }})</li>
{% endfor %}
</ul>

### Label sizes
{: #props-label-sizes}
<ul>
{% for label_size in site.shipcloud.supported_carriers.carrier_features.hermes.props.label_sizes %}
  <li>{{ label_size.name }} ({{ label_size.key }})</li>
{% endfor %}
</ul>

### Field lengths
{: #props-field-lengths}
<ul>
{% for field_length_entries in site.shipcloud.supported_carriers.carrier_features.hermes.props.field_lengths %}
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

## Hermes Shipping Interface

### Services
{: #hsi-services}
<ul>
{% for service in site.shipcloud.supported_carriers.carrier_features.hermes.hsi.services %}
  <li>{{ service.name }} ({{ service.key }})</li>
{% endfor %}
</ul>

### Additional services
{: #hsi-additional-services}
<ul>
{% for additional_service in site.shipcloud.supported_carriers.carrier_features.hermes.hsi.additional_services %}
  <li>{{ additional_service.name }} ({{ additional_service.key }})</li>
{% endfor %}
</ul>

### Package types
{: #hsi-package-types}
<ul>
{% for package_type in site.shipcloud.supported_carriers.carrier_features.hermes.hsi.package_types %}
  <li>{{ package_type.name }} ({{ package_type.key }})</li>
{% endfor %}
</ul>

### Label sizes
{: #hsi-label-sizes}
<ul>
{% for label_size in site.shipcloud.supported_carriers.carrier_features.hermes.hsi.label_sizes %}
  <li>{{ label_size.name }} ({{ label_size.key }})</li>
{% endfor %}
</ul>

### Field lengths
{: #hsi-field-lengths}

