#### Warenpost - National / International
{: #v3---dpag-warenpost}

When using the [Deutsche Post Warenpost](https://www.deutschepost.de/en/w/warenpost.html) as your
service you can send letters that will have shipment tracking and are usually delivered on the next
day.

__Requirements:__

- ```carrier``` has to be _'dpag'_
- ```package.type``` has to be _'parcel_letter'_
- ```service``` has to be _'dpag_warenpost'_
- The sender and recipient have to be located in Germany
- For shipments up to 1,000g
- Maximum dimensions: length 353mm, width 250mm, thickness 50mm
- Minimum volume: 200 items per year
- you'll have to use your own contract with the carrier

__Notice:__
Since this is a new offering of Deutsche Post, the tracking events returned by the carrier can
differ from the ones shown on the carriers' tracking page. We therefore advise you to send customers
to the carrier's tracking page for now until the carrier has figured out a way to return meaningful
tracking events.

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_warenpost_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_warenpost_togglebox_collapsable" class="panel-collapse collapse">
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
    "type": "parcel_letter"
  },
  "carrier": "dpag",
  "service": "dpag_warenpost",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
