---
layout: default
---

{% capture content %}
Welcome to the 2XKO section!

Use symbols like [[L]] and [[M]] in your text.
{% endcapture %}

{% assign content = content | markdownify %}

{% assign content = content | replace: '[[L]]', '<img src="{{ site.baseurl }}/assets/images/2xko_L.png" alt="L" style="height:1em;vertical-align:middle;">' %}
{% assign content = content | replace: '[[M]]', '<img src="{{ site.baseurl }}/assets/images/2xko_M.png" alt="M" style="height:1em;vertical-align:middle;">' %}

{{ content }}
