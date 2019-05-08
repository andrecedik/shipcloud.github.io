#### Post office delivery (Postfiliale)
{: #v2---postfiliale}

When sending to a DHL post office the following parameters have to be defined:

- `care_of` = customer id number (_postnummer_)
- `street` has to be `POSTFILIALE`
- `street_no` = number of the Postfiliale outlet

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_postfiliale_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_postfiliale_togglebox_collapsable" class="panel-collapse collapse">
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
    "care_of": "1234567",
    "street": "POSTFILIALE",
    "street_no": "515",
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
