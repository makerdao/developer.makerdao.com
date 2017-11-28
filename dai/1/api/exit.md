---
layout: dai/api
title: Dai
subtitle: API
---

## Exit

Withdraw collateral by returning `PETH` to the vault in exchange for the
proportional amount of `ETH`.

- The amount should be specified in units of `ETH`.
- PETH will be debited from the caller at the exit price (`bid`)

Will return more or less `ETH` tokens for each `PETH` than at `join` depending
whether the system made a profit or loss over the lifetime of the collateral
deposited to the pool.

![Join-Exit](https://user-images.githubusercontent.com/5028/30517891-928dd4d8-9bc1-11e7-9398-639233d851ae.png)

{% capture seth-cli %}
  $ seth send "{{ site.dai-tub }}" "exit(uint256)" "10.0"
{% endcapture %}

{% capture dai-cli %}
  $ dai exit 10.0
{% endcapture %}

{% capture py %}
  join(self, amount_in_gem: Wad) -> Transact:
{% endcapture %}

{% include tabs.html seth=seth-cli dai=dai-cli python=py %}
