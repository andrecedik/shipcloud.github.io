#### ShopDeliveryService
{: #web-api---drop-off-point}

> GLS delivers parcels (except tyres) directly to a ParcelShop. Recipients select in advance the ParcelShop to which the parcel should be sent.
> Once parcels have arrived, GLS informs recipients by e-mail or text message. They can collect their parcels from the GLS ParcelShop within the next eight working days after the day of delivery.

__Requirements:__

- `to.first_name` is mandatory
- `to.last_name` is mandatory
- `to.email` is mandatory
- `drop_off_point.drop_off_point_id` is mandatory (can be determined through the [GLS parcelshop search](https://gls-group.eu/DE/en/depot-parcelshop-search))
- `drop_off_point.type` has to be `parcel_shop`
- The sender has to be located in Austria, Belgium or Germany
- The recipient has to be located in one of the following countries: AT, DE, BE, DK, PL
- Only available when using GLS Web API integration

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_shopdeliveryservice_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_shopdeliveryservice_togglebox_collapsable" class="panel-collapse collapse">
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
    "first_name": "Karl",
    "last_name": "Müller",
    "street": "Musterstraße",
    "street_no": "14a",
    "city": "Paderborn",
    "zip_code": "33089",
    "country": "DE",
    "email": "receiver@mail.com",
    "phone": "0151-12345678",
    "drop_off_point": {
      "drop_off_point_id": "2760095246",
      "type": "parcel_shop"
    }
  },
  "package": {
    "weight": 0.5,
    "length": 20,
    "width": 15,
    "height": 5,
    "type": "parcel"
  },
  "service": "standard",
  "carrier": "gls",
  "label": {
    "size": "A5"
  },
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
