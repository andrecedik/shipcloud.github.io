#### Warenpost International (Untracked)
{: #v3---dpag-warenpost-untracked}

You can also send international shipments using the Warenpost service of Deutsche Post from outside 
of Germany. There are two different services you can use. The normal use case are tracked shipments 
using the service _'dpag_warenpost'_. You can also have international shipments without tracking 
information. For this you just specify the service to be _'dpag_warenpost_untracked'_.

__Requirements:__

- ```carrier``` has to be _'dpag'_
- ```package.type``` has to be _'parcel_letter'_
- ```service``` can be _'dpag_warenpost'_ or _'dpag_warenpost_untracked'_
- The sender has to be located in Germany
- The recipient has to be located outside of Germany
- Only applicable for shipments up to 2,000g
- Maximum dimensions: lenghth 600mm, width 600mm, length + width + thickness combined 900mm
- you'll have to use your own contract with the carrier

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_warenpost_untracked_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_warenpost_untracked_togglebox_collapsable" class="panel-collapse collapse">
<div class="well">
{% highlight http %}
POST https://api.shipcloud.io/v1/shipments
{% endhighlight %}

{% highlight json %}
{
  "from": {
    "company": "Sender Corp.",
    "first_name": "Susan",
    "last_name": "Sender",
    "street": "Sender Str.",
    "street_no": "99",
    "zip_code": "20148",
    "city": "Hamburg",
    "country": "DE"
  },
  "to": {
    "company": "Receiver AG",
    "first_name": "Roger",
    "last_name": "Receiver",
    "street": "Receiver Str.",
    "street_no": "1",
    "city": "Vienna",
    "zip_code": "1040",
    "country": "AT"
  },
  "package": {
      "weight": 0.5,
      "length": 40,
      "width": 20,
      "height": 10,
      "type": "parcel_letter"
  },
  "carrier": "dpag",
  "service": "dpag_warenpost_untracked",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
