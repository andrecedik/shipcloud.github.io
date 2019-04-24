#### DHL - Cash on delivery

__Requirements:__

- You'll have to use your own DHL contract

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
  "carrier": "dhl",
  "create_shipping_label": true
}
{% endhighlight %}
