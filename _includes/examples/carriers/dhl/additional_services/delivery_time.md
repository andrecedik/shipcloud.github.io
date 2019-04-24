#### DHL - Delivery Time (Preferred Time)

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

{% highlight http %}
POST https://api.shipcloud.io/v1/shipments
{% endhighlight %}
{% highlight json %}
{
  "carrier": "dhl",
  "from": {
    // see [1]
  },
  "to": {
    // see [1]
  },
  "package": {
    // see [2]
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
  "carrier": "dhl",
  "create_shipping_label": true
}
{% endhighlight %}
