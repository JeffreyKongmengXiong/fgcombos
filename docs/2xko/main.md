---
layout: default
---

{% comment %}
Define all symbol → image mappings here
Format: SYMBOL,IMAGE_PATH
Add more symbols as needed
{% endcomment %}
{% assign replacements = 
  "L,../assets/images/2xko_L.png|M,../assets/images/2xko_M.png" | split: "|" %}

{% comment %}
Define content blocks
You can add more captures for more sections
{% endcomment %}
{% capture content %}
Welcome to the 2XKO section!

Use symbols like [[L]] and [[M]] in your text.
{% endcapture %}

{% capture contenter %}
Another section: [[M]] and [[L]] appear again.
{% endcapture %}

{% capture content3 %}
Third section: [[L]] [[M]] [[L]].
{% endcapture %}

{% comment %}
Collect all content blocks in a list
{% endcomment %}
{% assign content_list = content | append: "|||" | append: contenter | append: "|||" | append: content3 | split: "|||" %}

{% assign processed_contents = "" %}

{% comment %}
Loop through each content block and apply all replacements
{% endcomment %}
{% for c in content_list %}
  {% assign temp = c %}
  {% for r in replacements %}
    {% assign parts = r | split: "," %}
    {% assign symbol = parts[0] %}
    {% assign path = parts[1] %}
    {% assign replacement = '<img src="' | append: path | append: '" alt="' | append: symbol | append: '" style="height:1em;vertical-align:middle;">' %}
    {% assign temp = temp | replace: "[[#{symbol}]]", replacement %}
  {% endfor %}
  {% assign processed_contents = processed_contents | append: temp | append: "<br>" | append: "<br>" %}
{% endfor %}

{{ processed_contents }}
