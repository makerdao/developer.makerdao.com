---
layout: dai/api
title: Dai
subtitle: API
---

## Cage

Cash in `dai` balance for ETH after `cage`.

![Cash](https://user-images.githubusercontent.com/5028/30519070-6cc4fd6a-9be1-11e7-92d8-5d965721d8ef.png)

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
