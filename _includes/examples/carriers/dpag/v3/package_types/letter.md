<h4 id="{{ include.carrier_interface | slugify }}---letter">Brief</h4>

If you want to send a simple [letter](https://www.deutschepost.de/en/b/brief_postkarte.html) using
the Deutsche Post AG services you can do that as well.

__Requirements:__

- ```package.type``` has to be _'letter'_
- ```carrier``` has to be _'dpag'_

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_package_type_letter_togglebox" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_package_type_letter_togglebox" class="panel-collapse collapse">
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
    "length": 14,
    "width": 10,
    "height": 0.3,
    "type": "letter"
  },
  "carrier": "{{page.carrier}}",
  "service": "standard",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
