## {{ site.data.carriers[page.carrier].interfaces.[include.carrier_interface].display_name }}
{: #{{ site.data.carriers[page.carrier].interfaces.[include.carrier_interface].display_name | slugify }}}

{% assign implementations=site.data.carriers[page.carrier].interfaces[include.carrier_interface].implementations.shipcloud %}

{% assign largest_array_size = 0 %}
{% for implementation in implementations %}
    {% assign implementation_name=implementation[0] %}
    {% assign entries=site.data.carriers[page.carrier].interfaces[include.carrier_interface].implementations.shipcloud.[implementation_name] %}
    {% if implementation_name != "field_lengths" and entries.size > largest_array_size %}
        {% assign largest_array_size = entries.size %}
    {% endif %}
{% endfor %}
{% assign largest_array_size = largest_array_size | minus: 1 %}

<table class="table table-striped table-hover table-bordered">
    <tr>
        <th>Services</th>
        <th>Package types</th>
        <th>Additional services</th>
        <th>Other Attributes</th>
        <th>Label sizes</th>
    </tr>
    {% for i in (0..largest_array_size) %}
    <tr>
        <td>
            {% assign services_entry = site.data.carriers[page.carrier].interfaces[include.carrier_interface].implementations.shipcloud.services[i] %}
            <a href="#{{include.carrier_interface | slugify }}---{{ services_entry.key | slugify }}">
                {{ services_entry.display_name }}
            </a>
        </td>
        <td>
            {% assign package_type_entry = site.data.carriers[page.carrier].interfaces[include.carrier_interface].implementations.shipcloud.package_types[i] %}
            <a href="#{{include.carrier_interface | slugify }}---{{ package_type_entry.key | slugify }}">
                {{ package_type_entry.display_name }}
            </a>
        </td>
        <td>
            {% assign additional_services_entry = site.data.carriers[page.carrier].interfaces[include.carrier_interface].implementations.shipcloud.additional_services[i] %}
            <a href="#{{include.carrier_interface | slugify }}---{{ additional_services_entry.key | slugify }}">
                {{ additional_services_entry.display_name }}
            </a>
        </td>
        <td>
            {% assign other_attributes_entry = site.data.carriers[page.carrier].interfaces[include.carrier_interface].implementations.shipcloud.other_attributes[i] %}
            <a href="#{{include.carrier_interface | slugify }}---{{ other_attributes_entry.key | slugify }}">
                {{ other_attributes_entry.display_name }}
            </a>
        </td>
        <td>
            {% assign label_size_entry = site.data.carriers[page.carrier].interfaces[include.carrier_interface].implementations.shipcloud.label_sizes[i] %}
            <a href="#{{include.carrier_interface | slugify }}---{{ label_size_entry.key | slugify }}">
                {{ label_size_entry.display_name }}
            </a>
        </td>
    </tr>
    {% endfor %}
</table>

{% assign entries=site.data.carriers[page.carrier].interfaces.[include.carrier_interface].implementations.shipcloud.services %}
{% if entries.size > 0 %}
### Services
{: #{{include.carrier_interface | slugify}}-services}
{% include utils/carrier_interface_entry_iterator.md entries=entries type='services' carrier_interface=include.carrier_interface %}
{% endif %}

{% assign entries=site.data.carriers[page.carrier].interfaces.[include.carrier_interface].implementations.shipcloud.package_types %}
{% if entries.size > 0 %}
### Package types
{: #{{include.carrier_interface | slugify}}-package-types}
{% include utils/carrier_interface_entry_iterator.md entries=entries %}
{% endif %}

{% assign entries=site.data.carriers[page.carrier].interfaces.[include.carrier_interface].implementations.shipcloud.additional_services %}
{% if entries.size > 0 %}
### Additional services
{: #{{include.carrier_interface | slugify}}-additional-services}
{% include utils/carrier_interface_entry_iterator.md entries=entries type='additional_services' carrier_interface=include.carrier_interface %}
{% endif %}

{% assign entries=site.data.carriers[page.carrier].interfaces.[include.carrier_interface].implementations.shipcloud.other_attributes %}
{% if entries.size > 0 %}
### Other attributes
{: #{{include.carrier_interface | slugify}}-other-attributes}
{% include utils/carrier_interface_entry_iterator.md entries=entries type='other_attributes' carrier_interface=include.carrier_interface %}
{% endif %}

{% assign entries=site.data.carriers[page.carrier].interfaces.[include.carrier_interface].implementations.shipcloud.label_sizes %}
{% if entries.size > 0 %}
### Label sizes
{: #{{include.carrier_interface | slugify}}-label-sizes}
{% include utils/carrier_interface_entry_iterator.md entries=entries %}
{% endif %}

{% assign entries=site.data.carriers[page.carrier].interfaces.[include.carrier_interface].implementations.shipcloud.field_lengths %}
{% if entries.size > 0 %}
### Field lengths
{: #{{include.carrier_interface | slugify}}-field-lengths}
{% include utils/json_level_iterator.md entries=entries %}
{% endif %}
