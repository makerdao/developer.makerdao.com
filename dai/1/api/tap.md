---
layout: dai/api
title: Dai
subtitle: API
---

### Debt Market

System surplus accumulates in the `tap` as excess `dai` which are sold in
exchange for collateral (`peth`) via `boom`.

Siezed collateral from forced liquidations (`peth`) is also sent to the `tap`
where it is sold for `dai` via `bust`.

### Tap - the liquidator

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
