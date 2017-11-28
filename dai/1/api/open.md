---
layout: dai/api
title: Dai
subtitle: API
---

## Open

Create an empty CDP and set the caller to be the owner.

![Open](https://user-images.githubusercontent.com/5028/30352570-b4c0f6a2-9874-11e7-8ca3-336531da4c0d.png)

{% capture seth-cli %}
  $ seth send "{{ site.dai-tub }}" "open()"
{% endcapture %}

{% capture dai-cli %}
  $ dai open
{% endcapture %}

{% capture py %}
  open(self) -> Transact:
{% endcapture %}

{% include tabs.html seth=seth-cli dai=dai-cli python=py %}

