---
layout: default
---

<img src="../assets/images/2xko_L.png">

{% capture content %}
Welcome to the 2XKO section!
<div style="text-align:center; border: 1px solid #d0d7de; border-radius: 8px; padding: 16px; display: inline-block;"> 
## Use symbols like [[L]] and [[M]] in your text.
</div>
{% endcapture %}

{% assign content = content | replace: '[[L]]', '<img src="../assets/images/2xko_L.png" alt="L" style="height:1em;vertical-align:middle;">' %}
{% assign content = content | replace: '[[M]]', '<img src="../assets/images/2xko_M.png" alt="M" style="height:1em;vertical-align:middle;">' %}

{{ content }}
