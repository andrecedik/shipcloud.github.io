#### Premium International
{: #v2---premium-international}

Using the additional service
<a href="https://www.dhl.de/en/paket/information/geschaeftskunden/premium.html" target="_blank" data-proofer-ignore>DHL premium international</a>
you can reduce international shipping transit times.

__Requirements:__

- You'll have to use your own DHL contract
- Your DHL contract must be setup for DHL "Ship" (DHL "Versenden")

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
      "name": "premium_international"
    }
  ],
  "carrier": "dhl",
  "create_shipping_label": true
}
{% endhighlight %}
