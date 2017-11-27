---
layout: dai/api
title: Dai
subtitle: API
---

## Shut

Close a CDP.

Collateral will be used to pay any outstanding debt at market rate. Remaining
collateral will be returned to the pool.

{% capture seth-cli %}
  $ seth send "{{ site.dai-tub }}" "shut(bytes32)" "<cup-id>"
{% endcapture %}

{% capture dai-cli %}
  $ dai --cup=<id> shut
{% endcapture %}

{% capture py %}
  shut(self, cup_id: int) -> Transact:
{% endcapture %}

{% include tabs.html seth=seth-cli dai=dai-cli python=py %}
