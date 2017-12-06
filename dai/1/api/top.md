---
layout: dai/api
title: Dai
subtitle: API
---

### Global Settlement

A key feature of Dai is the possibility of `cage`: shutting down the system
and reimbursing Dai holders. This is provided for easy upgrades between Dai
iterations, and for security in case of implementation flaws both in the code
and in the design.

#### Top

An admin can use the `top` contract to `cage` the system at a specific price
(dai per gem), or by reading the last price from the price feed.

First, sufficient real `gem` collateral is taken such that Dai holders can
redeem their Dai at face value. The `gem` is moved from the `tub` to the `tap`
and the `tap.cash` function is unlocked for Dai holders to call.

Any remaining `gem` remains in the `tub`. PETH holders can now `exit`.  CDP
holders must first `bite` their CDPs (although anyone can do this) and then
`free` their PETH.

Some important features of `cage`:

- Dai holders are not guaranteed their face value, only preferential payout.
- *the full real collateral pool is tapped* to make Dai whole. PETH is a
  *risk-bearing* token.
- PETH holders will receive a poor rate if they try to `exit` before all CDPs
  are processed by `bite`. To prevent accidental early `exit`, `top.flow` is
  provided, which will only enable `exit` after all CDPs are processed, or a
  timeout has expired.

The `top` also serves as a useful frontend entrypoint to the system, as it
links to all other components.
