#### Declared value
{: #ship-webservice---declared-value}

By using
<a href="https://www.ups.com/de/en/shipping/services/value-added/declared-value.page?loc=en_DE" target="_blank">
  UPS declared value
</a>
you can insure your parcel beyond the usual liability limits of EUR 510.

__Caution:__

- Additional fees will be charged by UPS. Check your UPS contract or ask your account manager to get
  a quote.
- You shouldn't specify "declared_value" when creating a shipment up to EUR 510 or lesser value
  unless you actually want the insurance instead of the liability.

__Requirements:__
- You'll have to use your own UPS contract

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_declared_value_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_declared_value_togglebox_collapsable" class="panel-collapse collapse">
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
    "length": 20,
    "width": 15,
    "height": 5,
    "type": "parcel",
    "declared_value": {
       "amount": 555.45,
       "currency": "EUR"
    }
  },
  "carrier": "{{page.carrier}}",
  "service": "standard",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
