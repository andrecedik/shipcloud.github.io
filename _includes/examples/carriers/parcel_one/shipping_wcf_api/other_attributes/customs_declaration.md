#### Customs declaration
{: #shipping-wcf-api---customs-declaration}

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
    "company": "Apple Inc.",
    "first_name": "Tim",
    "last_name": "Cook",
    "street": "Infinite Loop",
    "street_no": "1",
    "zip_code": "95014",
    "city": "Cupertino",
    "state": "CA",
    "country": "US",
    "phone": "408-996-1010"
  },
  "package": {
    "weight": "2",
    "length": "8",
    "width": "26",
    "height": "15",
    "type": "parcel"
  },
  "customs_declaration": {
    "contents_type": "commercial_goods",
    "contents_explanation": "Alcoholic beverages",
    "currency": "EUR",
    "additional_fees": 0.0,
    "drop_off_location": "DE",
    "posting_date": "2017-10-07",
    "invoice_number": "123ABC",
    "total_value_amount": 108.50,
    "items": [
      {
        "origin_country": "DE",
        "description": "Caol Ila 18 years",
        "hs_tariff_number": "123384890",
        "quantity": "1",
        "value_amount": "108.50",
        "net_weight": "0.8"
      }
    ]
  },
  "carrier": "{{page.carrier}}",
  "service": "standard",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>