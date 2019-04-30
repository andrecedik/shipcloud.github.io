#### Drop authorization
{: #shipment-service-3-2---drop-authorization}

When sending packages via DPD the sender can allow the carrier to leave the shipment with someone
else in case the receiver isn't present and has allowed the sender to do so.

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_drop_authorization_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_drop_authorization_togglebox_collapsable" class="panel-collapse collapse">
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
      "name": "drop_authorization",
      "properties": {
        "message": "Description about where the package should be left"
      }
    }
  ],
  "carrier": "dpd",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
