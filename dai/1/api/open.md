---
layout: dai/api
title: Dai
subtitle: API
---

## Open

Create an empty CDP and set the caller to be the owner.

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
