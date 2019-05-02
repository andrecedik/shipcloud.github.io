#### Saturday delivery
{: #rate-book---saturday-delivery}

When sending packages on a Friday you can specify that they should be delivered on Saturday (if
the carrier supports this).

__Requirements:__

- `service` has to be _'one_day'_ or _'one_day_early'_
- you'll have to use your own contract with the carrier

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_saturday_delivery_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_saturday_delivery_togglebox_collapsable" class="panel-collapse collapse">
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
      "name": "saturday_delivery"
    }
  ],
  "carrier": "{{page.carrier}}",
  "service": "one_day",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
