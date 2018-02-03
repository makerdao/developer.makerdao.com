---
layout: dai/api
title: Dai 1.0
subtitle: API - Boom
---

## Boom

Buy `dai` when the system is in surplus.

Can be thought of as buy and burn. Given a net Dai balance, sell the Dai in
return for PETH, which is burned.

![Boom](https://user-images.githubusercontent.com/5028/35772367-b3bd5194-09a1-11e8-9ecb-c5fa8b49df8f.png)

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
