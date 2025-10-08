---
layout: default
title: 2XKO Main Page
---

# 🌀 2XKO Main Page

{% capture content %}
Welcome to the 2XKO section!

Use symbols like [[L]] and [[M]] and [[H]] in your text.
{% endcapture %}

{% assign content = content | markdownify %}

{% assign content = content | replace: '[[L]]', '<img src="/assets/images/2xko_L.png" alt="L" style="height:1em;vertical-align:middle;">' %}
{% assign content = content | replace: '[[M]]', '<img src="assets/images/2xko_L.png" alt="M" style="height:1em;vertical-align:middle;">' %}
{% assign content = content | replace: '[[H]]', '<img src="/docs/assets/images/2xko_L.png" alt="H" style="height:1em;vertical-align:middle;">' %}

{{ content }}
