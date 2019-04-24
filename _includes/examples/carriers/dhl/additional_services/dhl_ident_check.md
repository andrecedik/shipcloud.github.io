#### DHL - Ident Check
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
      "name": "dhl_ident_check",
      "properties": {
        "first_name": "Hans",
        "last_name": "Dampf",
        "date_of_birth": "1982-09-30",
        "minimum_age": "16"
      }
    }
  ],
  "carrier": "dhl",
  "create_shipping_label": true
}
{% endhighlight %}
