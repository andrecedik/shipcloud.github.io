<h4 id="{{ include.carrier_interface | slugify }}---books">Büchersendung</h4>

You can send books, brochures, sheets of music and maps using the service
[Büchersendung](https://www.deutschepost.de/en/b/buechersendung_national.html) by Deutsche Post AG.

__Requirements:__

- ```package.type``` has to be _'books'_
- ```carrier``` has to be _'dpag'_

<a class="btn btn-primary" type="button" data-toggle="collapse" data-target="#{{include.carrier_interface}}_package_type_books_togglebox" aria-expanded="false" aria-controls="collapseExample">
  Show example
</a>

<div id="{{include.carrier_interface}}_package_type_books_togglebox" class="panel-collapse collapse">
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
    "length": 25,
    "width": 18,
    "height": 5,
    "type": "books"
  },
  "carrier": "{{page.carrier}}",
  "service": "standard",
  "create_shipping_label": true
}
{% endhighlight %}
</div>
</div>
