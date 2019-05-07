<h4 id="{{ include.carrier_interface | slugify }}---euro-pallet">Euro pallet</h4>

Use a [euro pallet (EPAL)](https://www.cargointernational.de/europalette) for sending goods via a
cheap pallet transport.

__Requirements:__

- max. dimensions 240 cm x 120 cm x 200 cm
- max. weight 1000 kg per pallet
- sender and recipient have to be located in Germany

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_package_type_euro_pallet_togglebox" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_package_type_euro_pallet_togglebox" class="panel-collapse collapse">
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
    "weight": "200",
    "length":"100",
    "width": "100",
    "height": "50",
    "type": "euro_pallet"
  },
  "carrier": "cargo_international",
  "service": "cargo_international_express",
  "description": "a short description of the shipment content",
  "reference_number": "order's reference number",
  "notification_email": "receiver@mail.com",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
