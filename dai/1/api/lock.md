---
layout: dai/api
title: Dai
subtitle: API
---

## Lock

Add `PETH` collateral (increases `ink`).

![Lock](https://user-images.githubusercontent.com/5028/30517892-928e06ec-9bc1-11e7-91e8-6ae6caae8585.png)

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
