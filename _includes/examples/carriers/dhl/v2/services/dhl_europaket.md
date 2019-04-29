#### Europaket
{: #v2---dhl-europaket}

The service [DHL Europaket](https://www.dhl.de/en/geschaeftskunden/paket/leistungen-und-services/internationaler-versand/europaket.html)
is a great solution for business-to-business parcel shipments, because shipments within the 32
supported countries will generally be delivered within 48 hours.

__Requirements:__

- minimum dimensions (l/w/h): 15 x 11 x 3.5 cm
- maximum dimensions (l/w/h): 120 x 60 x 60 cm
- maximum weight: 31.5 kg

<div class="panel-group" id="{{include.carrier_interface}}_dhl_europaket_togglebox">
  <div class="panel panel-default">
    <div class="panel-heading">
      <h4 class="panel-title">
        <a data-toggle="collapse" data-parent="#{{include.carrier_interface}}_dhl_europaket_togglebox" href="#{{include.carrier_interface}}_dhl_europaket_togglebox_collapsable">
          <i class="fas fa-chevron-down"></i> Example
        </a>
      </h4>
    </div>
    <div id="{{include.carrier_interface}}_dhl_europaket_togglebox_collapsable" class="panel-collapse collapse">
      <div class="panel-body">
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
  "service": "dhl_europaket",
  "create_shipping_label": true
}
{% endhighlight %}
      </div>
    </div>
  </div>
</div>
