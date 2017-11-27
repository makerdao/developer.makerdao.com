---
layout: dai/api
title: Dai
subtitle: API
---

## Bust

Sell `dai` when the system is in deficit.

{% capture seth-cli %}
  $ seth send "{{ site.dai-tub }}" "bust(uint256)" "<amount-in-skr>"
{% endcapture %}

{% capture dai-cli %}
  $ dai boom <amount-in-skr>
{% endcapture %}

{% capture py %}
  bust(self, amount_in_skr: Wad) -> Transact:
{% endcapture %}

{% include tabs.html seth=seth-cli dai=dai-cli python=py %}
