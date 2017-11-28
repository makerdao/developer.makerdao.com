---
layout: dai/default
title: Dai stable coin
---

## Introduction

Dai 1.0 (beta) is a stable coin implemented as an ERC20 token on the Ethereum
blockchain. Designed to maintain 1:1 parity with the US Dollar its value is
backed by collateral (`ether` in Dai 1.0) which is locked up in a smart contract
,the Maker collateral vault.

### Dai lifecycle

Dai is created by users borrowing against locked collateral and destroyed when
loans are repaid.

1. Anyone can create new `dai` by depositing `ether` as collateral and drawing
   off an appropriate amount of dai.
2. Locked collateral can be recovered at any time by paying back the borrowed
   `dai` (plus a stability fee).

Thus, all `dai` in circulation is at all times backed by at least as much
collateral. In fact the system only allows borrowing up to what Maker
governance considers to be a safe ratio (currently 150%) so USD $100M of dai in
circulation would for example be backed by at least USD $150M of ETH locked in
the Maker collateral vault.

### Debt/collateral ratio

The USD value of locked collateral will of course change over time. When the
value of collateral increases, borrowers are able to create new dai (up to the
safe ratio). When the USD value of collateral falls, borrowers can choose to
either repay borrowed dai, or deposit more collateral, as their position
approaches the liqudation ratio. Borrowers who allow their positions to fall
below the safe ratio risk forced liquidation.

Forced liquidation is Makers way of ensuring that the amount of collateral
backing circulating `dai` remains within safe parameters. Positions that fall
below the liquidation ratio can have their backing collateral seized and sold on
the Maker debt market for dai, which is then removed from circulation. In cases
of extreme volitility where the value of seized collateral may be insufficient
to cover the outstanding debt, the supply of collateral wrapper tokens is
expanded to cover any shortfall.

Note: Collateral holders can see their claim on the pool fall in value in
situations where the system has to cover any forced liquidations with a
negative debt ratio. Collateral holders in Dai 1.0 therefore carry the
responsability of backing the system through periods of volatility as well as
having the opportunity to profit when the system is healthy.

### Dai Users

For those seeking stability, the easiest way to obtain dai is to buy it on the
open market from cryptocurrecy exchanges. Regular users of Dai can use it as
money without having to interact with the advanced mechanics of the Dai
Stablecoin System. From their point of view, Dai is just another cryptocurrency
obtained from a cryptocurrency exchange or broker, that can be freely sent to
other users, used as payments for goods and services, or held as long term
savings.

### Dai Borrowers

Those seeking risk, and the opportunity for profit can borrow dai against
locked collateral by operating a CDP (Collateralised Debt Position). A CDP is
simply lightweight record which tracks a particular borrowing position - the
owner of the position, the amount of locked collateral, and the amount of
dai which has been issued.
