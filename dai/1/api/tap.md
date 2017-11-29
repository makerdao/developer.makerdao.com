---
layout: dai/api
title: Dai
subtitle: API
---

## Debt Market

Boom: Debt in exchange for collateral

- the system sells profits in exchange for peth (claim on collateral), which it burns.
- the value of peth relative to collateral increases
- the supply of dai increases
- collateral is backing more debt, reflected by the change in supply ratio to peth.

Bust: Collateral in exchange for debt

- the system sells collateral from underwater positions (dai) in exchange for dai, which it burns
- where recovered collateral is insufficient it mints more, increasing the peth supply
- value of peth relative to collateral decreases
- the supply of dai decreases
- less debt being backed by collateral, reflected by the change in supply ratio to peth.

Both operations levy a spread - ?%

#### The Liquidator

The `tap` is a liquidator. It has three token balances that determine its
allowed behaviour:

- `joy`: Dai balance, surplus transferred from `drip`
- `woe`: Sin balance, bad debt transferred from `bite`
- `fog`: PETH balance, collateral pending liquidation

and one derived price, `s2s`, which is the price of PETH in Dai. The `tap`
seeks to minimise all of its token balances. Recall that Dai can be canceled
out with Sin via `heal`.

The `tap` has two acts:

- `boom`: sell Dai in return for PETH (decreases `joy` and `woe`, decreases PETH
  supply)
- `bust`: sell PETH in return for Dai (decreases `fog`, increases `joy` and
  `woe`, can increase PETH supply)

Through `boom` and `bust` we close the feedback loop on the price of
PETH. When there is surplus Dai, PETH is burned, decreasing the PETH supply
and increasing `per`, giving PETH holders more GEM per PETH. When there is
surplus Woe, PETH is inflated, increasing the PETH supply and decreasing
`per`, giving PETH holders less GEM per PETH.

The reason for wrapping GEM in PETH is now apparent: *it provides a way
to socialise losses and gains incurred in the operation of the system.*

Two features of this mechanism:

1. Whilst PETH can be inflated significantly, there is a finite limit on
   the amount of bad debt the system can absorb - given by the value of
   the underlying GEM collateral.

2. There is a negative feedback between `bust` and `bite`: as PETH is
   inflated it becomes less valuable, reducing the safety level of CDPs.
   Some CDPs will become unsafe and be vulnerable to liquidation,
   creating more bad debt. In an active market, CDP holders will have to
   be vigilant about the potential for PETH inflation if they are holding
   tightly collateralised CDPs.
