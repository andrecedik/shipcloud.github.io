#### Europaket
{: #v2---dhl-europaket}

The service [DHL Europaket](https://www.dhl.de/en/geschaeftskunden/paket/leistungen-und-services/internationaler-versand/europaket.html)
is a great solution for business-to-business parcel shipments, because shipments within the 32
supported countries will generally be delivered within 48 hours.

__Requirements:__

- minimum dimensions (l/w/h): 15 x 11 x 3.5 cm
- maximum dimensions (l/w/h): 120 x 60 x 60 cm
- maximum weight: 31.5 kg

{% highlight http %}
POST https://api.shipcloud.io/v1/shipments
{% endhighlight %}

{% highlight json %}
{
  "from": {
    "first_name": "Roger",
    "last_name": "Receiver",
    "street": "Receiver Str.",
    "street_no": "1",
    "city": "Hamburg",
    "zip_code": "20535",
    "country": "DE"
  },
  "to": {
    "first_name": "Serge",
    "last_name": "Sender",
    "company": "Sender Corp.",
    "street": "Sender Str.",
    "street_no": "99",
    "zip_code": "20148",
    "city": "Hamburg",
    "country": "DE"
  },
  "package": {
    "weight": 0.5,
    "length": 20,
    "width": 15,
    "height": 5,
    "type": "parcel"
  },
  "carrier": "dhl",
  "service": "dhl_europaket",
  "create_shipping_label": true
}
{% endhighlight %}
