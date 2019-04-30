#### Parcel letter
{: #shipment-service-3-2---parcel-letter}

DPD defines parcel letters as "everything which is too small for a parcel but larger and heavier 
than a classical letter"

__Requirements:__

- `package.type` has to be _'parcel_letter'_

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_parcel_letter_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_parcel_letter_togglebox_collapsable" class="panel-collapse collapse">
<div class="well">
{% highlight http %}
POST https://api.shipcloud.io/v1/shipments
{% endhighlight %}

{% highlight json %}
{
  "from": {
    "first_name": "Serge",
    "last_name": "Sender",
    "company": "Sender Corp.",
    "street": "Sender Str.",
    "street_no": "99",
    "zip_code": "20148",
    "city": "Hamburg",
    "country": "DE"
  },
  "to": {
    "first_name": "Roger",
    "last_name": "Receiver",
    "street": "Receiver Str.",
    "street_no": "1",
    "city": "Hamburg",
    "zip_code": "20535",
    "country": "DE"
  },
  "package": {
    "weight": 0.5,
    "length": 25,
    "width": 36,
    "height": 5,
    "type": "parcel_letter"
  },
  "carrier": "dpd",
  "service": "standard",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
