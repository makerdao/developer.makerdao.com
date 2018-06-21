---
layout: default
title: Keepers
subtitle: incentive-following bots
description: Compete for profit opportunities created by the Maker system
---

### Introduction

The Maker system provides various opportunities for profit which help to
maintain market equilibrium. Strategies to arbitrage these opportunities can be
codified as keepers - automated bots which can detect and trade inefficiencies
across Dai Core, OasisDEX and various other exchanges.

It is expected that developers and operators will evolve their own keepers over
time. Below you will find a list of our reference keepers.

Bear in mind that this page is just a brief summary of reference keepers and that
you can find out more by reading individual keeper READMEs present in
[their GitHub repositories](https://github.com/search?p=1&q=topic%3Amaker-keeper+org%3Amakerdao&type=Repositories),
or even by directly reading their source code which is usually quite well documented.
We encourage developers to hack existing keeper implementations and to build new ones,
either using the [pymaker](https://github.com/makerdao/pymaker) and
[pyexchange](https://github.com/makerdao/pyexchange) libraries or completely from
scratch. Due to profit opportunities inherent to the Maker ecosystem we expect
the keeper space to grow over time.

The community is always happy to answer your questions in the
[#keeper](https://chat.makerdao.com/channel/keeper){:target="_blank"} RocketChat channel.


### bite-keeper

CDPs that fall below the safe collateralization ratio can be liquidated by any
external agent via an operation known as [bite]({{ "dai/1/api/bite" |
relative_url }}).

The **[bite-keeper](https://github.com/makerdao/bite-keeper)** constantly monitors
the `Tub` contract looking for unsafe cups and bites them the moment they
become unsafe. In future versions, it will take into account the profit it can
make by processing the liquidated collateral via [bust]({{ "dai/1/api/bust" |
relative_url }}) and only waste gas on bite if it can make it up by subsequent
arbitrage. For now, it's just a dumb keeper that bites any cups that become
unsafe.


### arbitrage-keeper

The **[arbitrage-keeper](https://github.com/makerdao/arbitrage-keeper)** performs
arbitrage on OasisDEX, `join`, `exit`, `boom` and `bust` actions. It constantly
scans for profitable arbitrage opportunities and executes them the moment they
become available. Although a bit dated, it provides valuable source of information
where to look for arbitrage opportunities in the Dai system and how to exploit them.
It also supports atomic risk-free arbitrage via the [tx-manager](https://github.com/makerdao/tx-manager)
contract.

The **arbitrage-keeper** will not work with multicollateral Dai, mainly because
`boom` and `bust` actions will not be present in it anymore. Instead of that,
surplus and bad debt will be liquidated via auctions. Please see the `auction-keeper` below.


### auction-keeper

The **[auction-keeper](https://github.com/makerdao/auction-keeper)** is currently
early work in progress, we plan to make it fully functional by the time of the
multicollateral Dai launch. It will support surpus and bad debt auctions in multicollateral Dai.


### market-maker-keeper

The **[market-maker-keeper](https://github.com/makerdao/market-maker-keeper)** is actually
a set of keepers that facilitate market making on multiple exchanges. They all follow
the same configuration principles, and almost all of them are capable of covering
any DAI market provided an appropriate price feed is present.

As of today, the following exchanges are supported:
* OasisDEX,
* EtherDelta,
* RadarRelay and ERCdEX (via [Standard Relayer API](https://github.com/0xProject/standard-relayer-api)),
* Paradex,
* DDEX,
* Ethfinex,
* GoPax,
* HitBTC,
* IDEX,
* Bibox,
* OKEX,
* gate.io.


### cdp-keeper

The **[cdp-keeper](https://github.com/makerdao/cdp-keeper)** is responsible for
actively monitoring and managing open CDPs. In early versions it was only capable
only of topping up CDPs at risk of falling below the liquidation level, but
more functionality started being added to allow:

- automatically wiping debt when approaching the liquidatio ratio
- managing the dai volume to keep it within specific range

This keeper is still under development.
