#### Customs declaration using CN22
{: #v3---customs-declaration}

If you want to send a shipment to a country where a customs declaration is necessary you can specify
this the following way. Detailed information about the parameters can be found in our
[documentation of creating a shipment]({{ site.baseurl }}/reference/#shipments).

__Requirements:__

- `customs_declaration.contents_type` is mandatory
- `customs_declaration.currency` has to be _'EUR'_
- `customs_declaration.items` is mandatory

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_customs_declaration_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_customs_declaration_togglebox_collapsable" class="panel-collapse collapse">
<div class="well">
{% highlight http %}
POST https://api.shipcloud.io/v1/shipments
{% endhighlight %}

{% highlight json %}
{
  "from": {
    "company": "Sender Inc",
    "first_name": "Serge",
    "last_name": "Sender",
    "street": "Senderstr.",
    "street_no": "99",
    "city": "Hamburg",
    "zip_code": "20148",
    "country": "DE"
  },
  "to": {
      "company": "Receiver Inc.",
      "first_name": "Rolf",
      "last_name": "Receiver",
      "street": "Pennsylvania Ave NW",
      "street_no": "1600",
      "city": "Washington D.C.",
      "zip_code": "20500",
      "state": "DC",
      "country": "US",
  },
  "package": {
      "weight": 1.5,
      "length": 30,
      "width": 15,
      "height": 5,
      "type": "parcel_letter"
  },
  "customs_declaration": {
    "contents_type": "commercial_goods",
    "contents_explanation": "Goods for sale",
    "currency": "EUR",
    "total_value_amount": 150,
    "items": [{
        "origin_country": "DE",
        "description": "Linkwood 25 years",
        "hs_tariff_number": "62032280",
        "quantity": 1,
        "value_amount": 70,
        "net_weight": 1.0
      },
      {
        "origin_country": "DE",
        "description": "Caol Ila 18 years",
        "hs_tariff_number": "62032280",
        "quantity": 1,
        "value_amount": 80,
        "net_weight": 0.5
      }
    ]
  },
  "carrier": "dpag",
  "service": "dpag_warenpost",
  "create_shipping_label": true
} 
{% endhighlight %}
</div>
</div>
