---
layout: default
---

{% comment %}
Define all symbol → image mappings here.
Format: SYMBOL,IMAGE_PATH
Add more symbols as needed.
{% endcomment %}
{% assign replacements = 
  "L,../assets/images/2xko_L.png|M,../assets/images/2xko_M.png" | split: "|" %}

{% comment %}
Define your content blocks below.
You can add as many as you want.
{% endcomment %}
{% capture content %}
Welcome to the 2XKO section!

Use symbols like [[L]] and [[M]] in your text.
{% endcapture %}

{% capture contenter %}
Another section! Use [[M]] here too, and even [[L]] again.
{% endcapture %}

{% capture content3 %}
Third section: [[L]] [[M]] [[L]] again.
{% endcapture %}

{% comment %}
Collect all content blocks into a list
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
    {% assign temp = temp | replace: "[[#{symbol}]]", '<img src="' | append: path | append: '" alt="' | append: symbol | append: '" style="height:1em;vertical-align:middle;">' %}
  {% endfor %}
  {% assign processed_contents = processed_contents | append: temp | append: "<br>" %}
{% endfor %}

{{ processed_contents }}
