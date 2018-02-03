---
layout: dai/api
title: Dai 1.0
subtitle: API - Free
---

## Free

Remove `PETH` collateral (decreases `ink`).

![Free](https://user-images.githubusercontent.com/5028/35772482-61a6330a-09a4-11e8-94e1-910253b5a5a1.png)

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
