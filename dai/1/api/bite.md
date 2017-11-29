---
layout: dai/api
title: Dai
subtitle: API
---

## Bite

Liquidate a vunerable CDP (zeros `art`, decreases `ink`).

Unsafe CDPs need to be liquidated. When a `cup` is not `safe`, anyone can
perform `bite(cup)`, which takes on all CDP debt and confiscates sufficient
collateral to cover this, plus a buffer.

This returns the CDP to a safe state (possibly with zero collateral).

There are other possible implementations of `bite`, e.g. only taking
sufficient collateral to just transition the CDP to safe, but the
described implementation is chosen for simplicity.

![Bite](https://user-images.githubusercontent.com/5028/30519068-6c871ed2-9be1-11e7-83df-3cbda6a49e3b.png)

{% capture seth-cli %}
  $ seth send "{{ site.dai-tub }}" "bite(bytes32)" "<cup-id>"
{% endcapture %}

{% capture dai-cli %}
  $ dai --cup=<id> bite
{% endcapture %}

{% capture py %}
  bite(self, cup_id: int) -> Transact:
{% endcapture %}

{% include tabs.html seth=seth-cli dai=dai-cli python=py %}
