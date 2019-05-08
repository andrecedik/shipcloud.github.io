#### Rules
{: #{{ include.carrier_interface | slugify }}---{{ include.type | slugify }}}

- if one of the following conditions is true, the parameter `description` is mandatory:
  - `from` and `to` countries are not the same
  - `from` and/or `to` countries are not in the EU
  - `from` and `to` countries are in the EU and the shipments service is not `standard`
