---
layout: dai/api
title: Dai
subtitle: API
---

## Free

Remove collateral from a CDP.

{% capture seth-cli %}
  $ seth send "{{ site.dai-tub }}" "free(bytes32,uint256)" "<cup-id>" "<amount-in-skr>"
{% endcapture %}

{% capture dai-cli %}
  $ dai --cup=<id> free <amount-in-skr>
{% endcapture %}

{% capture py %}
  free(self, cup_id: int, amount_in_skr: Wad) -> Transact:
{% endcapture %}

{% include tabs.html seth=seth-cli dai=dai-cli python=py %}
