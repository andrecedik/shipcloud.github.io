#### Delivery Time (Preferred Time)
{: #v2---delivery-time}

With the
[DHL preferred time service](https://www.dhl.de/en/paket/information/geschaeftskunden/service-wunschzeit.html)
you can choose between several two-hour time frames for
the delivery of your item. The following options are available for ```time_of_day_earliest``` and
```time_of_day_latest``` (Monday - Saturday):

* Nationwide in Germany for evening deliveries:
  * 18:00 - 20:00
  * 19:00 - 21:00
* In specific German conurbations for daytime deliveries:
  * 10:00 - 12:00
  * 12:00 - 14:00
  * 14:00 - 16:00
  * 16:00 - 18:00

__Requirements:__

- You'll have to use your own DHL contract
- Your DHL contract must be setup for DHL "Ship" (DHL "Versenden")
- The recipient has to be located in Germany
- Only available for label size A5

<div class="panel-group" id="{{include.carrier_interface}}_delivery_time_togglebox">
  <div class="panel panel-default">
    <div class="panel-heading">
      <h4 class="panel-title">
        <a data-toggle="collapse" data-parent="#{{include.carrier_interface}}_delivery_time_togglebox" href="#{{include.carrier_interface}}_delivery_time_togglebox_collapsable">
          <i class="fas fa-chevron-down"></i> Example
        </a>
      </h4>
    </div>
    <div id="{{include.carrier_interface}}_delivery_time_togglebox_collapsable" class="panel-collapse collapse">
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
      "name": "delivery_time",
      "properties": {
          "time_of_day_earliest": "18:00",
          "time_of_day_latest": "20:00"
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
