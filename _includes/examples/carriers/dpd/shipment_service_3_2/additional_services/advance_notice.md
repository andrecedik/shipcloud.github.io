#### Predict
{: #shipment-service-3-2---advance-notice}

DPD allows recipients to be notified of a pending delivery within the next hour. The so called
predict service can be used with shipcloud by specifying it as an additional service. You can either 
specify the email address or phone number of your customer to be notified.

__Requirements:__

- `service` has to be _'standard'_

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_predict_email_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show notification via email example
</a>
<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_predict_sms_togglebox_collapsable" aria-expanded="false" aria-controls="collapseExample">
  Show notification via sms example
</a>

<div id="{{include.carrier_interface}}_predict_email_togglebox_collapsable" class="panel-collapse collapse">
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
      "name": "advance_notice",
      "properties": {
        "email": "test@example.com",
        "language": "en"
      }
    }
  ],
  "carrier": "dhl",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>

<div id="{{include.carrier_interface}}_predict_sms_togglebox_collapsable" class="panel-collapse collapse">
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
      "name": "advance_notice",
      "properties": {
        "sms": "+4917012345678"
      }
    }
  ],
  "carrier": "dpd",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
