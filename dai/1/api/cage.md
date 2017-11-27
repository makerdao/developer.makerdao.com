---
layout: dai/api
title: Dai
subtitle: API
---

## Cage

Lock the system and initiate settlement.

{% capture seth-cli %}
  $ seth send "{{ site.dai-top }}" "cage(uint256)" "<final-price>"
{% endcapture %}

{% capture dai-cli %}
  $ dai cage [<final-price>]
{% endcapture %}

{% capture py %}
  # not implemented
{% endcapture %}

{% include tabs.html seth=seth-cli dai=dai-cli python=py %}
