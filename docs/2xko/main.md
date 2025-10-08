---
layout: default
---

{% capture content %}
Welcome to the 2XKO section!

Use symbols like [[L]] and [[M]] in your text.
{% endcapture %}

{{ content | replace: 'Use', '<img src="{{ site.baseurl }}/assets/images/2xko_L.png" alt="L" style="height:1em;vertical-align:middle;">' }}

{{ content | replace: 'Use', '<img src="/docs/assets/images/2xko_L.png" alt="L" style="height:1em;vertical-align:middle;">' }}

{{ content | replace: 'Use', '<img src="assets/images/2xko_L.png" alt="L" style="height:1em;vertical-align:middle;">' }}

{{ content }}
