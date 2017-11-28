---
layout: dai/api
title: Dai
subtitle: API
---

## Cage

Lock the system and initiate settlement.

![Cage](https://user-images.githubusercontent.com/5028/30519069-6c9ae656-9be1-11e7-9e3f-e75f585024f7.png)

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
