---
layout: dai/api
title: Dai
subtitle: API
---

## Cage

Cash in `dai` balance for ETH after `cage`.

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
