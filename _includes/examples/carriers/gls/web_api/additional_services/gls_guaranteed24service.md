#### Guaranteed24Service
{: #web-api---gls-guaranteed24service}

When using the additional service
<a href="https://gls-group.eu/DE/de/versand-services/guaranteed-24-service" target="_blank">Guaranteed24Service</a>
the carrier GLS is guaranteeing delivery on the next business day (except Saturdays) for shipments
within Germany. If the delivery can't be made within time, GLS will refund the extra charges for
the service.

__Requirements:__

- Only applicable for shipments within Germany
- The sender and recipient have to be located in Germany
- You'll have to use your own contract with the carrier
- Only available when using GLS Web API integration

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_guaranteed24service_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_guaranteed24service_togglebox_collapsable" class="panel-collapse collapse">
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
      "name": "gls_guaranteed24service"
    }
  ],
  "service": "standard",
  "carrier": "gls",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
