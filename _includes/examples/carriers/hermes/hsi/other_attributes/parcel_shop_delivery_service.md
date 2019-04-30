#### ParcelShopDeliveryService
{: #hsi---parcel-shop-delivery-service}

__Requirements:__

- You have to use your own (Hermes HSI) carrier contract
- `drop_off_point.drop_off_point_id` is mandatory (can be determined through the [Hermes Website](https://www.myhermes.de/paketshop/))
- `drop_off_point.type` has to be `parcel_shop`

__Options:__

- Hermes can notify the receiver via sms or email if you provide the additional service
  [advance notice](#hermes---customer-alert)

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_parcel_shop_delivery_service_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_parcel_shop_delivery_service_togglebox_collapsable" class="panel-collapse collapse">
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
    "company": "Hermes Paketshop Schmidt",
    "care_of": "3. Liftstock",
    "street": "Receiver Str.",
    "street_no": "1",
    "city": "Hamburg",
    "zip_code": "20535",
    "country": "DE",
    "drop_off_point": {
      "drop_off_point_id": "660328",
      "type": "parcel_shop"
    }
  },
  "package": {
    "weight": "2.5",
    "length": "40",
    "width": "20",
    "height": "10",
    "type": "parcel"
  },
  "service": "standard",
  "carrier": "hermes",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
