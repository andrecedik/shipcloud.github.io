#### Cash on delivery
{: #v2---cash-on-delivery}

__Requirements:__

- You'll have to use your own DHL contract

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_cash_on_delivery_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_cash_on_delivery_togglebox_collapsable" class="panel-collapse collapse">
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
      "name": "cash_on_delivery",
      "properties": {
        "amount": 123.45,
        "currency": "EUR",
        "bank_account_holder": "Max Mustermann",
        "bank_name": "Musterbank",
        "bank_account_number": "DE12500105170648489890",
        "bank_code": "BENEDEPPYYY",
        "reference1": "reason for transfer"
      }
    }
  ],
  "carrier": "{{page.carrier}}",
  "service": "standard",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>