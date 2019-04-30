#### Cargo International Express
{: #{{include.carrier_interface}}---cargo-international-express}

Express shipment that will be delivered the next working day

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_cargo_international_express_togglebox" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_cargo_international_express_togglebox" class="panel-collapse collapse">
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
  "carrier": "{{page.carrier}}",
  "service": "cargo_international_express",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
