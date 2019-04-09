---
title: Carrier specific things
nav: carriers
---

# Carriers

## Supported carriers
<ul>
{% for carrier in site.shipcloud.supported_carriers.as_list %}
  <li><a href="{{ carrier.key | prepend: site.baseurl }}">{{ carrier.name }}</a></li>
{% endfor %}
</ul>

## Supported services
{% assign props_services_keys = site.shipcloud.supported_carriers.carrier_features.hermes.props.services | map: "key" %}
{% assign hsi_services_keys = site.shipcloud.supported_carriers.carrier_features.hermes.hsi.services | map: "key" %}
{% assign services = props_services_keys | concat: hsi_services_keys | uniq %}
<ul>
{% for service in services %}
  <li>{{ service }}</li>
{% endfor %}
</ul>
<!-- {{ site.shipcloud.supported_carriers.as_list }} -->
<!-- {{ site.shipcloud.supported_carriers.as_keys_array }} -->
