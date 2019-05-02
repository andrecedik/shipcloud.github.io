#### Expedited
{: #ship-webservice---ups-expedited}

If you want to send less urgent shipments to destinations outside of Europe you can use the UPS
service
<a href="https://www.ups.com/de/en/shipping/international/services/expedited.page?loc=en_DE" target="_blank">
  expedited
</a>
to reach more than 220 countries and territories.

__Requirements:__
- `description` is mandatory
- `service` has to be _'ups_expedited'_
- You’ll have to use your own UPS contract
- The recipient has to be located outside of the EU, Liechtenstein, Norway or Switzerland

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_expedited_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_expedited_togglebox_collapsable" class="panel-collapse collapse">
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
    "company": "Apple Inc.",
    "first_name": "Tim",
    "last_name": "Cook",
    "care_of": null,
    "street": "Infinite Loop",
    "street_no": "1",
    "zip_code": "95014",
    "city": "Cupertino",
    "state": "CA",
    "country": "US",
    "phone": "408-996-1010"
  },
  "package": {
    "weight": 0.5,
    "length": 20,
    "width": 15,
    "height": 5,
    "type": "parcel"
  },
  "carrier": "{{page.carrier}}",
  "service": "ups_expedited",
  "description": "Linkwood 25 years",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
