#### Customs declaration
{: #v2---customs-declaration}

If you want to send a shipment to a country where a customs declaration is necessary you can specify
this the following way. Detailed information about the parameters can be found in our
[documentation of creating a shipment]({{ site.baseurl }}/reference/#shipments).

__Requirements:__

- `customs_declaration.currency` has to be _'EUR'_

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
    "weight": 0.5,
    "length": 20,
    "width": 15,
    "height": 5,
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
    "total_value_amount": 247,
    "items": [{
        "origin_country": "DE",
        "description": "Linkwood 25 years",
        "hs_tariff_number": "501293884",
        "quantity": "1",
        "value_amount": "138.50",
        "net_weight": "0.8"
      },
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

Response

{% highlight json %}
{
  "id": "199f803bf82fab79e17654213b61993fa78b0524",
  "carrier": "dhl",
  "carrier_tracking_no": "84168117830018",
  "tracking_url": "https://track.shipcloud.io/de/199f803bf8",
  "label_url": "https://sc-labels.s3.amazonaws.com/shipments/01370b4d/199f803bf8/label/shipping_label_199f803bf8.pdf",
  "price": 10.7,
  "customs_declaration": {
    "id": "cd-f466905c",
    "contents_type": "commercial_goods",
    "contents_explanation": "Alcoholic beverages",
    "invoice_number": "123ABC",
    "drop_off_location": "DE",
    "posting_date": "2017-10-07",
    "additional_fees": "0.0",
    "total_value_amount": "247.0",
    "currency": "EUR",
    "created_at": "2017-10-04T15:49:44+02:00",
    "updated_at": "2017-10-04T15:49:44+02:00",
    "carrier_declaration_document_url": "https://documents.shipcloud.io/shipments/519895c7165cdc032356d42c6d9babe8e3151473/customs_declaration_document.pdf",
    "items": [{
        "id": "cdi-50a46bf8",
        "description": "Linkwood 25 years",
        "hs_tariff_number": "501293884",
        "net_weight": 0.8,
        "origin_country": "DE",
        "quantity": 1,
        "value_amount": "138.5",
        "created_at": "2017-10-04T15:49:44+02:00",
        "updated_at": "2017-10-04T15:49:44+02:00"
      },
      {
        "id": "cdi-081a523d",
        "description": "Caol Ila 18 years",
        "hs_tariff_number": "123384890",
        "net_weight": 0.8,
        "origin_country": "DE",
        "quantity": 1,
        "value_amount": "108.5",
        "created_at": "2017-10-04T15:49:44+02:00",
        "updated_at": "2017-10-04T15:49:44+02:00"
      }
    ]
  }
}
{% endhighlight %}
</div>
</div>