#### Appointment announcement
{: #{{include.carrier_interface}}---advance-notice}

If you want the recipient to get a call from the carrier some time before the shipment will arrive
at its destination you can specify the phone number of the recipient via our additional service
advance_notice.

__Requirements:__

- `service` has to be _'standard'_
- `package.type` can be _'disposable_pallet'_, _'euro_pallet'_ or
  _'cargo_international_large_parcel'_

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_advance_notice_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_advance_notice_togglebox_collapsable" class="panel-collapse collapse">
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
    "weight": 40,
    "length": 1200,
    "width": 800,
    "height": 144,
    "type": "euro_pallet"
  },
  "additional_services": [
    {
      "name": "advance_notice",  
      "properties": {  
        "phone": "015112345678"  
      }
    }
  ],
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
