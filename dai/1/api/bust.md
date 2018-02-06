---
layout: dai/api
title: Dai 1.0
subtitle: API - Bust
---

## Bust

Sell `dai` when the system is in deficit.

`bust` is really two functions in one: collateral sell off (aka `flip`),
and inflate and sell (aka `flop`). When `fog` is non zero it is sold in
return for Dai, which is used to cancel out the bad debt, `woe`. If
`fog` is zero but the `tap` has a net Sin balance, then PETH is minted
and sold in return for Dai, up to the point that the net Sin balance is
zero.

![Bust](https://user-images.githubusercontent.com/5028/35772382-2587365a-09a2-11e8-8bde-57787d494236.png)

{% capture seth-cli %}
  $ seth send "{{ site.dai-tub }}" "bust(uint256)" "<amount-in-skr>"
{% endcapture %}

{% capture dai-cli %}
  $ dai bust <amount-in-skr>
{% endcapture %}

{% capture py %}
  bust(self, amount_in_skr: Wad) -> Transact:
{% endcapture %}

{% include tabs.html seth=seth-cli dai=dai-cli python=py %}
