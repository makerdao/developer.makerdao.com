---
layout: dai/api
title: Dai 1.0
subtitle: API - Cash
---

## Cage

Cash in `dai` balance for ETH after `cage`.

![Cash](https://user-images.githubusercontent.com/5028/35772766-8d34ae08-09a8-11e8-83d5-a13c5a323322.png)

{% capture seth-cli %}
  $ seth send "{{ site.dai-top }}" "cash(uint256)" "<dai-balance>"
{% endcapture %}

{% capture dai-cli %}
  $ dai cash
{% endcapture %}

{% capture py %}
  # not implemented
{% endcapture %}

{% include tabs.html seth=seth-cli dai=dai-cli python=py %}
