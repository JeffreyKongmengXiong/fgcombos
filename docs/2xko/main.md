---
layout: default
---

<img src="../assets/images/2xko_L.png">

Welcome to the 2XKO section!

{% capture content %}
Use symbols like [[L]] and [[M]] in your text.


{% endcapture %}

{% capture contenter %}
Another section: [[M]] and [[L]] appear again.


{% endcapture %}

{% capture content3 %}
Third section: [[L]] [[M]] [[L]].


{% endcapture %}

{% assign content = content | replace: '[[L]]', '<img src="../assets/images/2xko_L.png" alt="L" style="height:1em;vertical-align:middle;">' %}
{% assign content = content | replace: '[[M]]', '<img src="../assets/images/2xko_M.png" alt="M" style="height:1em;vertical-align:middle;">' %}

{% assign replacements = "L,../assets/images/2xko_L.png|M,../assets/images/2xko_M.png" | split: "|" %}
{% assign content_list = content | append: "|||" | append: contenter | append: "|||" | append: content3 | split: "|||" %}
{% assign processed_contents = "" %}


{% for c in content_list %}
  {% assign temp = c %}
  {% for r in replacements %}
    {% assign parts = r | split: "," %}
    {% assign symbol = parts[0] %}
    {% assign path = parts[1] %}
    {% assign temp = temp | replace: "[[#{symbol}]]", '<img src="'' | append: path | append: '" alt="' | append: symbol | append: '" style="height:1em;vertical-align:middle;">' %}
  {% endfor %}
  {% assign processed_contents = processed_contents | append: temp | append: "<br>" %}
{% endfor %}

{{ processed_contents }}

{{ content }}
