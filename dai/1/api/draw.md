---
layout: dai/api
title: Dai
subtitle: API
---

## Draw

Issue a specified amount of `dai`

{% capture seth-cli %}
  $ seth send "{{ site.dai-tub }}" "draw(bytes32,uint256)" "<cup-id>" "<amount-in-dai>"
{% endcapture %}

{% capture dai-cli %}
  $ dai --cup=<id> draw <amount-in-dai>
{% endcapture %}

{% capture py %}
  draw(self, cup_id: int, amount_in_sai: Wad) -> Transact:
{% endcapture %}

{% include tabs.html seth=seth-cli dai=dai-cli python=py %}
