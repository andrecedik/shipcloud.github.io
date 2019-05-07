#### Tracking number
{: #{{ include.carrier_interface | slugify }}---{{ include.type | slugify }}}

Shipments will receive a carrier tracking number (`carrier_tracking_no`) with the first scan by the 
carrier, which is why this parameter won't be included in the response when creating a shipment.
