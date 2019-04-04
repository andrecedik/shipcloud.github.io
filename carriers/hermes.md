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

### Other attributes
{: #props-other-attributes}

### Field lengths
{: #props-field-lengths}

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

### Other attributes
{: #hsi-other-attributes}

### Field lengths
{: #hsi-field-lengths}

