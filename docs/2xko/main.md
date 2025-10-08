---
layout: default
title: 2XKO Main Page
---

# 🌀 2XKO Main Page

Welcome to the 2XKO section!

{% capture content %}
Welcome to the 2XKO section!

Use symbols like [[L]] and [[M]] in your text.
{% endcapture %}

{% assign content = content | replace: '[[L]]', '<img src="/assets/images/2xko_L.png" alt="L" style="height:1em;vertical-align:middle;">' %}
{% assign content = content | replace: '[[M]]', '<img src="/docs/assets/images/2xko_M.png" alt="M" style="height:1em;vertical-align:middle;">' %}

{{ content | markdownify }}
