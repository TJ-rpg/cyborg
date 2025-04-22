# {{ page.title }}
{: .text-right}

#### {{ page.region}} - {{ page.timestamp | date: "%B %-d" }} 
{: .text-right}

{% if page.narration %}

{% assign filename = page.path | split: '/' | last | replace: '.md', ''%}
{% for entry in page.narration %}
{% assign to_include = filename | append: "_" | append: entry | append: ".md" %}
<details close markdown="block">
  <summary id="index">
    <b>{{ entry }}'s accounts</b><br> 
  </summary>
{: .text-delta}
{% include_relative {{ to_include }} %}
</details>
{% endfor %}
{% endif %}

