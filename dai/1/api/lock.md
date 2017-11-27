---
layout: dai/api
title: Dai
subtitle: API
---

## Lock

Add `PETH` collateral to a CDP.

{% capture seth-cli %}
  $ seth send "{{ site.dai-tub }}" "lock(bytes32,uint256)" "<cup-id>" "<amount-in-skr>"
{% endcapture %}

{% capture dai-cli %}
  $ dai --cup=<id> lock <amount-in-skr>
{% endcapture %}

{% capture py %}
  lock(self, cup_id: int, amount_in_skr: Wad) -> Transact:
{% endcapture %}

{% include tabs.html seth=seth-cli dai=dai-cli python=py %}
