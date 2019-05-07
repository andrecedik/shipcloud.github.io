#### Shipments with Pickup Requests
{: #{{ include.carrier_interface | slugify }}---{{ include.type | slugify }}}

If you don't have regular pickups by DHL Express you will have to request a pickup when creating a
shipment. Therefore, you can add a pickup element to your shipment request.

__Requirements:__

- the date for `pickup_time.earliest` and `pickup_time.latest` has to be the same
- supplying a `pickup_address` is optional
- supplying a `description` is mandatory
- supplying `phone` is mandatory for sender and recipient addresses
- `state` has to be 2 characters long

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_{{ include.type }}_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_{{ include.type }}_togglebox_collapsable" class="panel-collapse collapse">
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
    "state": "HH",
    "country": "DE"
  },
  "to": {
    "first_name": "Roger",
    "last_name": "Receiver",
    "street": "Receiver Str.",
    "street_no": "1",
    "city": "Hamburg",
    "state": "HH",
    "zip_code": "20535",
    "country": "DE"
  },
  "package": {
      "weight": 1.5,
      "length": 20,
      "width": 20,
      "height": 20
  },
  "pickup": {
    "pickup_time": {
      "earliest": "2015-09-15T09:00:00+02:00",
      "latest": "2015-09-15T18:00:00+02:00"
    },
    "pickup_address": {
      "company": "Sender Ltd.",
      "first_name": "Jane",
      "last_name": "Doe",
      "street": "Musterstraße",
      "street_no": "42",
      "zip_code": "54321",
      "city": "Musterstadt",
      "country": "DE"
     }
  },
  "description": "Important goods that need to be delivered fast!",
  "carrier": "{{ page.carrier }}",
  "service": "one_day",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
