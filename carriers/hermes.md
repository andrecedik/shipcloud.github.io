---
title: Hermes @ shipcloud
nav: carriers

---

# Hermes

## Profi Paketservice

### Services
{: #props-services}
<ul>
{% for service in site.data.carriers.hermes.interfaces.props.implementations.shipcloud.services %}
  <li>{{ service.name }} ({{ service.key }})</li>
{% endfor %}
</ul>

### Additional services
{: #props-additional-services}
<ul>
{% for additional_service in site.data.carriers.hermes.interfaces.props.implementations.shipcloud.additional_services %}
  <li>{{ additional_service.name }} ({{ additional_service.key }})</li>
{% endfor %}
</ul>

### Package types
{: #props-package-types}
<ul>
{% for package_type in site.data.carriers.hermes.interfaces.props.implementations.shipcloud.package_types %}
  <li>{{ package_type.name }} ({{ package_type.key }})</li>
{% endfor %}
</ul>

### Label sizes
{: #props-label-sizes}
<ul>
{% for label_size in site.data.carriers.hermes.interfaces.props.implementations.shipcloud.label_sizes %}
  <li>{{ label_size.name }} ({{ label_size.key }})</li>
{% endfor %}
</ul>

### Field lengths
{: #props-field-lengths}
{% include utils/field_lengths_display.md carrier_name="hermes" carrier_interface="props"%}

## Hermes Shipping Interface

### Services
{: #hsi-services}
<!-- <ul>
{% for service in site.shipcloud.supported_carriers.carrier_features.hermes.hsi.services %}
  <li>{{ service.name }} ({{ service.key }})</li>
{% endfor %}
</ul> -->

<ul>
{% for service in site.data.carriers.hermes.interfaces.hsi.implementations.shipcloud.services %}
  <li>{{ service.name }} ({{ service.key }})</li>
{% endfor %}
</ul>

### Additional services
{: #hsi-additional-services}
<ul>
{% for additional_service in site.data.carriers.hermes.interfaces.hsi.implementations.shipcloud.additional_services %}
  <li>{{ additional_service.name }} ({{ additional_service.key }})</li>
{% endfor %}
</ul>

### Package types
{: #hsi-package-types}
<ul>
{% for package_type in site.data.carriers.hermes.interfaces.hsi.implementations.shipcloud.package_types %}
  <li>{{ package_type.name }} ({{ package_type.key }})</li>
{% endfor %}
</ul>

### Label sizes
{: #hsi-label-sizes}
<ul>
{% for label_size in site.data.carriers.hermes.interfaces.hsi.implementations.shipcloud.label_sizes %}
  <li>{{ label_size.name }} ({{ label_size.key }})</li>
{% endfor %}
</ul>

### Field lengths
{: #hsi-field-lengths}
{% include utils/field_lengths_display.md carrier_name="hermes" carrier_interface="hsi"%}

<!-- {{ site.data.carriers.hermes.interfaces.hsi }} -->
