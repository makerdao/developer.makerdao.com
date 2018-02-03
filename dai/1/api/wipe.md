---
layout: dai/api
title: Dai 1.0
subtitle: API - Wipe
---

## Wipe

Repay some portion of oustanding Dai debt (decreases `art`, `rum`).

![Wipe](https://user-images.githubusercontent.com/5028/35772639-a8391ad2-09a7-11e8-9230-2528d3e3a804.png)

{% capture seth-cli %}
  $ seth send "{{ site.dai-tub }}" "wipe(bytes32,uint)" "<cup-id>" "<amount-in-dai>"
{% endcapture %}

{% capture dai-cli %}
  $ dai --cup=<id> wipe <amount-in-dai>
{% endcapture %}

{% capture py %}
  wipe(self, cup_id: int, amount_in_sai: Wad) -> Transact:
{% endcapture %}

{% include tabs.html seth=seth-cli dai=dai-cli python=py %}
