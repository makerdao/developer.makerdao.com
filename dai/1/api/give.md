---
layout: dai/api
title: Dai
subtitle: API
---

## Give

Transfer a CDP to a different owner. (changes `lad`)

![Give](https://user-images.githubusercontent.com/5028/30352570-b4c0f6a2-9874-11e7-8ca3-336531da4c0d.png)

{% capture seth-cli %}
  $ seth send "{{ page.dai-tub }}" "give(bytes32,address)" "<cup-id>" "<new-owner-address>"
{% endcapture %}

{% capture dai-cli %}
  $ dai --cup=<id> give <address>
{% endcapture %}

{% capture py %}
  give(self, cup_id: int, new_lad: Address) -> Transact:
{% endcapture %}

{% include tabs.html seth=seth-cli dai=dai-cli python=py %}
