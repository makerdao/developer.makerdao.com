---
layout: default
title: Keepers
subtitle: incentive-following bots
description: Compete for profit opportunities created by the Maker system
---

### Introduction

The Maker system provides various opportunities for profit which help to
maintain market equilibrium. Strategies to arbitrage these opportunities can be
codeified as keepers - automated bots which can detect and trade inefficienies
across Dai Core, Oasis and USD exchanges.

It is expected that developers and operators will evolve their own keepers over
time. Here are a few of our reference keepers for inspiration:

### Bite

CDPs that fall below the safe collateralization ratio can be liquidated by any
external agent via an operation known as [bite]({{ "dai/1/api/bite" |
relative_url }})

The [Bite Keeper](https://github.com/makerdao/bite-keeper) constantly monitors
the Dai Tub contract looking for unsafe cups and bites them the moment they
become unsafe. In future versions, it will take into account the profit it can
make by processing the liquidated collateral via [bust]({{ "dai/1/api/bust" |
relative_url }}) and only waste gas on bite if it can make it up by subsequent
arbitrage. For now, it's just a dumb keeper that bites any cups that become
unsafe.

### CDP Maintenance

The [CDP Keeper](https://github.com/makerdao/cdp-keeper) is responsible for
actively monitoring and managing open CDPs. In early versions it was only capable
only of topping up CDPs at risk of falling below the liquidation level, but
more functionality is curently being added to allow:

- automatically wiping debt when approaching the liquidatio ratio
- managing the dai volume to keep it within specific range

This keeper is still under development.

### Arbitrage

The [Arbitrage Keeper](https://github.com/makerdao/arbitrage-keeper) performs
arbitrage on OasisDex, `join`, `exit`, `boom` and `bust` actions. It constantly
scans for profitable arbitrage opportunities and executes them the moment they
become available.

### Market Makers

Market making keepers for OasisDex, EtherDelta and RadarRelay.

[Market Makers](https://github.com/makerdao/market-maker-keeper) is a set of
keepers that facilitate DAI/W-ETH and DAI/ETH market making on the following
exchanges:

* OasisDex
* EtherDelta
* RadarRelay
