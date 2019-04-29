#### Visual age check
{: #v2---visual-age-check}

When sending goods that are only legally available for people of a specific age, you can request
the carrier to check the receiver's age visually. Just add the additional service
`visual_age_check` and either `16` or `18` as its `minimum_age` value.

__Requirements:__

- You need to use your own DHL Ship contract
- The recipient has to be located in Germany

<div class="panel-group" id="{{include.carrier_interface}}_visual_age_check_togglebox">
  <div class="panel panel-default">
    <div class="panel-heading">
      <h4 class="panel-title">
        <a data-toggle="collapse" data-parent="#{{include.carrier_interface}}_visual_age_check_togglebox" href="#{{include.carrier_interface}}_visual_age_check_togglebox_collapsable">
          <i class="fas fa-chevron-down"></i> Example
        </a>
      </h4>
    </div>
    <div id="{{include.carrier_interface}}_visual_age_check_togglebox_collapsable" class="panel-collapse collapse">
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
      "name": "visual_age_check",
      "properties": {
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
