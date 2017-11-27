---
layout: dai/api
title: Dai
subtitle: API
---

## Boom

Buy `dai` when the system is in surplus.

{% capture seth-cli %}
  $ seth send "{{ site.dai-tub }}" "boom(uint256)" "<amount-in-skr>"
{% endcapture %}

{% capture dai-cli %}
  $ dai boom <amount-in-skr>
{% endcapture %}

{% capture py %}
  boom(self, amount_in_skr: Wad) -> Transact:
{% endcapture %}

{% include tabs.html seth=seth-cli dai=dai-cli python=py %}
