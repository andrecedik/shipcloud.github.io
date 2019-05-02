#### FlexDeliveryService
{: #web-api---advance-notice}

> The <a href="https://gls-group.eu/DE/en/flexdelivery" target="_blank">FlexDeliveryService</a> gives recipients numerous possibilities to customise parcel delivery.
> [...]
> The recipient gets information via e-mail about the upcoming parcel delivery, including the estimated delivery time frame. If the recipient will not be at home, he can choose from a range of practical delivery options – actively influencing the delivery of the parcel.

__Requirements:__
- `service` has to be `standard`
- `properties.email` is mandatory
- Can be used for shipments from Austria, Belgium, Denmark and Germany to the following countries:
  AT, BE, CZ, DE, DK, ES, FR, HR, HU, LU, NL, PL, RO, SI, SK
- Only available when using GLS Web API integration

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_flexdeliveryservice_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_flexdeliveryservice_togglebox_collapsable" class="panel-collapse collapse">
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
      "name": "advance_notice",
      "properties": {
        "email": "test@example.com",
        "sms": "+4917012345678"
      }
    }
  ],
  "service": "standard",
  "carrier": "gls",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
