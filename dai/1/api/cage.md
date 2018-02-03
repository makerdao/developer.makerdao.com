---
layout: dai/api
title: Dai 1.0
subtitle: API - Cage
---

## Cage

Lock the system and initiate settlement.

![Cage](https://user-images.githubusercontent.com/5028/35772757-52fe000e-09a8-11e8-81da-edb5406fe43c.png)

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
