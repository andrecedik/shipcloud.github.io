---
title: DHL @ shipcloud
nav: carriers
---

# DHL

## DHL Api V2.1

### Services
{: #dhl-v2-services}
<ul>
{% for service in site.data.carriers.dhl.interfaces.v2.implementations.shipcloud.services %}
  <li>{{ service.name }} ({{ service.key }})</li>
{% endfor %}
</ul>

### Additional services
{: #dhl-v2-additional-services}
<ul>
{% for service in site.data.carriers.dhl.interfaces.v2.implementations.shipcloud.additional_services %}
  <li>{{ service.name }} ({{ service.key }})</li>
{% endfor %}
</ul>

### Package types
{: #dhl-v2-package-types}
<ul>
{% for service in site.data.carriers.dhl.interfaces.v2.implementations.shipcloud.package_types %}
  <li>{{ service.name }} ({{ service.key }})</li>
{% endfor %}
</ul>

### Label sizes
{: #dhl-v2-label-sizes}
<ul>
{% for service in site.data.carriers.dhl.interfaces.v2.implementations.shipcloud.label_sizes %}
  <li>{{ service.name }} ({{ service.key }})</li>
{% endfor %}
</ul>

### Other attributes
{: #dhl-v2-other-attributes}

### Field lengths
{: #dhl-v2-field-lengths}
{% include utils/field_lengths_display.md carrier_name="dhl" carrier_interface="v2"%}

## DHL Api V3

### Services
{: #dhl-v3-services}

### Additional services
{: #dhl-v3-additional-services}

### Package types
{: #dhl-v3-package-types}

### Label sizes
{: #dhl-v3-label-sizes}

### Other attributes
{: #dhl-v3-other-attributes}

### Field lengths
{: #dhl-v3-field-lengths}
