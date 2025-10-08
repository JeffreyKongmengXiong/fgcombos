---
layout: default
---

<img src="../assets/images/2xko_L.png">
<img src="/docs/assets/images/2xko_L.png">
<img src="assets/images/2xko_L.png">

{% capture content %}
Welcome to the 2XKO section!

Use symbols like [[L]] and [[M]] in your text.
{% endcapture %}

{
  "product": {
    "featured_image": "docs/assets/images/2xko_L.png"
  }
}

{{ product.featured_image }}

{{ content | replace: 'Use', 'Doo' }}

{{ content | replace: 'Use', '<img src="/docs/assets/images/2xko_L.png">' }}

{{ content | replace: 'Use', '<img src="assets/images/2xko_L.png">' }}

{{ content }}
