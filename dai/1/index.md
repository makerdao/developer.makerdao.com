---
layout: default
title: Dai
subtitle: stable coin
description: Distributed Autonymous Insured
---

## Introduction

Dai 1.0 (beta) is a stable coin implemented as an ERC20 token on the Ethereum
blockchain. Designed to maintain 1:1 parity with the US Dollar its value is
backed by collateral (`ether` in Dai 1.0) which is locked up in a smart contract
, the Maker collateral vault.

The dai life-cycle:

1. Anyone can create new `dai` by depositing `ether` as collateral and drawing
   off an appropriate amount of dai.
2. Locked collateral can be recovered at any time by paying back the borrowed
   `dai` (plus a stability fee).

Thus, all `dai` in circulation is at all times backed by at least as much
collateral. In fact the system only allows borrowing up to what Maker governance
considers to be a safe ratio (currently 150%) so USD $10M of dai in circulation
would for example be backed by at least USD $15M of ETH locked in the collateral
vault.

The USD value of locked collateral will of course change over time. When the
value of collateral increases, borrowers are able to create new dai (up to the
safe ratio). When the USD value of collateral falls, borrowers may have to
either repay borrowed dai, or deposit more collateral, as their position
approaches the liqudation ratio. Borrowers who allow their positions to fall
below the safe ratio risk forced liquidation.

Forced liquidation is Makers way of ensuring that the amount of collateral
backing circulating `dai` remains within safe parameters. Positions that fall
below the liquidation ratio can have their backing collateral seized and sold on
the Maker debt market for dai, which is then removed from circulation. In cases
of extreme volitility where the amount of seized collateral may be insufficient
to cover the outstanding debt, the supply of collateral backing tokens is
expanded to cover any shortfall.

It is by ensuring that all new `dai` is issued 1:1[^i] for each USD of backing
collateral and that the amount of backing collateral is always within safe
parameters, that the system seeks to maintain equilibrium.

### Dai Borrowers

CDP operators.

Seeking risk. Bring new dai into circulation.

### Dai Users

Seeking stability.

Buy dai on the open market.

[^i]: conceptually - target price may fluctuate in practice depending on
  market conditions
