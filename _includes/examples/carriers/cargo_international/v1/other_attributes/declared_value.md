#### Additional insurance
{: #{{include.carrier_interface}}---declared-value}

An additional insurance beyond legal liablity of 10 EUR/kg can be booked by using the
`declared_value` parameter.

__Requirements:__

- the object `declared_value` has to be specified stating the amount and currency of the shipment

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
    "weight": 40,
    "length": 1200,
    "width": 800,
    "height": 144,
    "type": "euro_pallet",
    "declared_value": {
      "amount": 5000,
      "currency": "EUR"
     }
  },
  "carrier": "cargo_international",
  "service": "standard",
  "description": "a short description of the shipment content",
  "reference_number": "order's reference number",
  "notification_email": "receiver@mail.com",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
