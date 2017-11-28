---
layout: dai/api
title: Dai
subtitle: API
---

## Wipe

Repay some portion of oustanding Dai debt (decreases `art`, `rum`).

![Wipe](https://user-images.githubusercontent.com/5028/30463893-97a6aef4-9a22-11e7-9a65-3055ad05b8d6.png)

{% capture seth-cli %}
  $ seth send "{{ site.dai-tub }}" "wipe(bytes32,uint256)" "<cup-id>" "<amount-in-dai>"
{% endcapture %}

{% capture dai-cli %}
  $ dai --cup=<id> wipe <amount-in-dai>
{% endcapture %}

{% capture py %}
  wipe(self, cup_id: int, amount_in_sai: Wad) -> Transact:
{% endcapture %}

{% include tabs.html seth=seth-cli dai=dai-cli python=py %}
