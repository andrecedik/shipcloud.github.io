#### Parcel pickup station (Packstation)
{: #v2---packstation}

When sending to a DHL Packstation the following parameters have to be defined:

- `care_of` = customer id number (_postnummer_)
- `street` has to be `PACKSTATION`
- `street_no` = number of packstation

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_packstation_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_packstation_togglebox_collapsable" class="panel-collapse collapse">
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
    "first_name": "Hans",
    "last_name": "Meier",
    "care_of": "12345678",
    "street": "PACKSTATION",
    "street_no": "109",
    "city": "Hamburg",
    "zip_code": "20148",
    "country": "DE"
  },
  "package": {
    "weight": 0.5,
    "length": 20,
    "width": 15,
    "height": 5,
    "type": "parcel"
  },
  "carrier": "dhl",
  "service": "standard",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
