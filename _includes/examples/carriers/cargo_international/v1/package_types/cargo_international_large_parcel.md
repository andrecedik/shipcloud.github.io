<h4 id="{{ include.carrier_interface | slugify }}---{{ page.carrier | slugify }}-large-parcel">Large parcel</h4>

__Requirements:__

- max. dimensions 320 cm x 200 cm x 200 cm
- max. girth 700cm
- max. weight 100 kg
- max. dimensional weight: 800kg
- sender and recipient have to be located in Germany
- `service` can be _'standard'_ or _'cargo_international_express'_
- `package.type` has to be _'cargo_international_large_parcel'_

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_package_type_large_parcel_togglebox" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_package_type_large_parcel_togglebox" class="panel-collapse collapse">
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
    "weight": "100",
    "length":"120",
    "width": "60",
    "height": "30",
    "type": "cargo_international_large_parcel"
  },
  "carrier": "cargo_international",
  "service": "standard",
  "description": "a short description of the shipment content",
  "reference_number": "order's reference number",
  "notification_email": "receiver@mail.com",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
