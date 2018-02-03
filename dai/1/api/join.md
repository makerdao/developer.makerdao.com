---
layout: dai/api
title: Dai 1.0
subtitle: API - Join
---

## Join

Join the collateral pool by depositing `ETH` in exchange for `PETH` (pooled
ether).

- The amount should be specified in units of `PETH`.
- ETH will be debited from the caller at the join price (`ask`)

![Join-Exit](https://user-images.githubusercontent.com/5028/35772451-cba0bb78-09a3-11e8-8f8e-fc8d6ecbad3e.png)

{% capture seth-cli %}
  $ seth send "{{ site.dai-tub }}" "join(uint256)" "10.0"
{% endcapture %}

{% capture dai-cli %}
  $ dai join 10.0
{% endcapture %}

{% capture py %}
  join(self, amount_in_gem: Wad) -> Transact:
{% endcapture %}


{% include tabs.html seth=seth-cli dai=dai-cli python=py %}
