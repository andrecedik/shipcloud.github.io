#### Incoterms
{: #web-api---incoterms}

To be able to send dutiable shipments you have to send GLS the shipment specific incoterm with your
request.

__Requirements:__

- `incoterm` is mandatory, its value can be `ddp`, `ddp_untaxed`, `dap` or `dap_cleared`

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_incoterms_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_incoterms_togglebox_collapsable" class="panel-collapse collapse">
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
    "first_name": "Daniel",
    "last_name": "Bernoulli",
    "street": "Rue du Grand-Pré",
    "street_no": "2a",
    "city": "Lausanne",
    "zip_code": "1007",
    "country": "CH"
  },
  "package": {
    "weight": 0.5,
    "length": 20,
    "width": 15,
    "height": 5,
    "type": "parcel"
  },
  "service": "standard",
  "carrier": "{{page.carrier}}",
  "incoterm": "ddp",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
