---
layout: dai/api
title: Dai 1.0
subtitle: API - Draw
---

## Draw

Issue a specified amount of Dai (increases `art`, `rum`)

![Draw](https://user-images.githubusercontent.com/5028/35772639-a8391ad2-09a7-11e8-9230-2528d3e3a804.png)

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
