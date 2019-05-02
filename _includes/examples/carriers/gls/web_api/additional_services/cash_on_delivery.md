#### Cash on delivery
{: #web-api---cash-on-delivery}

> Cash on delivery parcels with GLS: The recipient pays for the goods on delivery in cash. GLS
> accepts the money and transfers it securely and quickly to the sender’s account – usually within
> five working days after delivery.

__Requirements:__

- Maximum cash on delivery amount and liability limit: € 2,500
- The Currency has to be EUR
- The sender has to be located in Germany or Austria
- The recipient has to be located in Germany or Austria
- You'll have to use your own contract with the carrier
- Only available when using GLS Web API integration

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_cash_on_delivery_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_cash_on_delivery_togglebox_collapsable" class="panel-collapse collapse">
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
    "type": "parcel"
  },
  "additional_services": [
    {
      "name": "cash_on_delivery",
      "properties": {
        "amount": 123.45,
        "currency": "EUR",
        "reference1": "reason for transfer"
      }
    }
  ],
  "carrier": "{{page.carrier}}",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
