---
title: Carrier specific things
nav: carriers
---

# Carriers

## Supported carriers
<ul>
{% for carrier in site.shipcloud.supported_carriers.as_list %}
  <li><a href="{{ carrier.key | prepend: site.baseurl }}" data-proofer-ignore>{{ carrier.name }}</a></li>
{% endfor %}
</ul>

## Supported services
{% assign props_services_keys = site.data.carriers.hermes.interfaces.props.implementations.shipcloud.services | map: "key" %}
{% assign hsi_services_keys = site.data.carriers.hermes.interfaces.hsi.implementations.shipcloud.services | map: "key" %}
{% assign dhl_v2_services_keys = site.data.carriers.dhl.interfaces.v2.implementations.shipcloud.services | map: "key" %}
{% assign services = props_services_keys | concat: hsi_services_keys | uniq %}
<ul>
{% for service in services %}
  <li>{{ service }}</li>
{% endfor %}
</ul>
<!-- {{ site.shipcloud.supported_carriers.as_list }} -->
<!-- {{ site.shipcloud.supported_carriers.as_keys_array }} -->
