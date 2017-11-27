---
layout: dai/api
title: Dai
subtitle: API
---

## Bite

Liquidate a vunerable CDP.

{% capture seth-cli %}
  $ seth send "{{ site.dai-tub }}" "bite(bytes32)" "<cup-id>"
{% endcapture %}

{% capture dai-cli %}
  $ dai --cup=<id> bite
{% endcapture %}

{% capture py %}
  bite(self, cup_id: int) -> Transact:
{% endcapture %}

{% include tabs.html seth=seth-cli dai=dai-cli python=py %}
