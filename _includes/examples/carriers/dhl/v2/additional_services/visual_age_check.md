#### Visual age check
{: #v2---visual-age-check}

When sending goods that are only legally available for people of a specific age, you can request
the carrier to check the receiver's age visually. Just add the additional service
`visual_age_check` and either `16` or `18` as its `minimum_age` value.

__Requirements:__

- You need to use your own DHL Ship contract
- The recipient has to be located in Germany

{% highlight http %}
POST https://api.shipcloud.io/v1/shipments
{% endhighlight %}
{% highlight json %}
{
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
      "name": "visual_age_check",
      "properties": {
        "minimum_age": "16"
      }
    }
  ],
  "carrier": "dhl",
  "create_shipping_label": true
}
{% endhighlight %}
