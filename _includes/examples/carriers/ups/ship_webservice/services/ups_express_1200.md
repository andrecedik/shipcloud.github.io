#### Express 12:00
{: #ship-webservice---standard}

The UPS service [Express 12:00](https://www.ups.com/de/en/shipping/services/intra/express-1200.page?loc=en_DE)
ensures a next business day delivery by noon throughout the country.

__Requirements:__

- The sender and recipient have to be located in Germany
- ```service``` has to be _'ups_express_1200'_
- Label size can be A5 & A6

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_express_1200_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_express_1200_togglebox_collapsable" class="panel-collapse collapse">
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
  "carrier": "{{page.carrier}}",
  "service": "ups_express_1200",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
