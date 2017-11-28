---
layout: dai/api
title: Dai
subtitle: API
---

## Boom

Buy `dai` when the system is in surplus.

Can be thought of as buy and burn. Given a net Dai balance, sell the Dai in
return for PETH, which is burned.

![Boom](https://user-images.githubusercontent.com/5028/30517887-924bec1c-9bc1-11e7-8c25-6d73a1c48340.png)

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
