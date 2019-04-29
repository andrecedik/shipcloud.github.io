#### Ident Check
{: #v2---dhl-ident-check}

If you want the carrier to only deliver the shipment to a specific person you can use the DHL ident
check. DHL will ask the recepient to show them a valid ID. Thus you will be able to minimize fraud,
only deliver to persons of a certain age (e.g. when sending alcoholic beverages, adult content or
pharmaceuticals that need a prescription).

__Caution:__
- Please keep in mind that additional fees will be charged by DHL. Check your DHL contract or ask
  your DHL Account Manager to get a quote.

__Requirements:__

- You'll have to use your own DHL contract
- Your DHL contract must be setup for DHL "Ship" (DHL "Versenden")
- The recipient has to be located in Germany
- Only available for label size A5

<div class="panel-group" id="{{include.carrier_interface}}_dhl_ident_check_togglebox">
  <div class="panel panel-default">
    <div class="panel-heading">
      <h4 class="panel-title">
        <a data-toggle="collapse" data-parent="#{{include.carrier_interface}}_dhl_ident_check_togglebox" href="#{{include.carrier_interface}}_dhl_ident_check_togglebox_collapsable">
          <i class="fas fa-chevron-down"></i> Example
        </a>
      </h4>
    </div>
    <div id="{{include.carrier_interface}}_dhl_ident_check_togglebox_collapsable" class="panel-collapse collapse">
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
  "additional_services": [
    {
      "name": "dhl_ident_check",
      "properties": {
        "first_name": "Hans",
        "last_name": "Dampf",
        "date_of_birth": "1982-09-30",
        "minimum_age": "16"
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
  </div>
</div>
