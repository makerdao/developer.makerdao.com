---
layout: dai/api
title: Dai
subtitle: API
---

## Bust

Sell `dai` when the system is in deficit.

`bust` is really two functions in one: collateral sell off (aka `flip`),
and inflate and sell (aka `flop`). When `fog` is non zero it is sold in
return for Dai, which is used to cancel out the bad debt, `woe`. If
`fog` is zero but the `tap` has a net Sin balance, then PETH is minted
and sold in return for Dai, up to the point that the net Sin balance is
zero.

![Bust](https://user-images.githubusercontent.com/5028/30517888-9287dd76-9bc1-11e7-8726-6b21843e27a5.png)

{% capture seth-cli %}
  $ seth send "{{ site.dai-tub }}" "bust(uint256)" "<amount-in-skr>"
{% endcapture %}

{% capture dai-cli %}
  $ dai boom <amount-in-skr>
{% endcapture %}

{% capture py %}
  bust(self, amount_in_skr: Wad) -> Transact:
{% endcapture %}

{% include tabs.html seth=seth-cli dai=dai-cli python=py %}
