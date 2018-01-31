---
layout: dai/default
title: Dai stability
---

### Stability

Dai 1.0 seeks to maintain stable value relative to a reference; the US Dollar.

To this end, the system must ensure that the amount of Dai in circulation is at
all times backed by at least the equivalent USD amount of collateral.

In order to achieve this:

- Collateral is valued using a reference price, `ETHUSD`, (`pip`) which is
  provided by a trusted [external oracle]({{ "feeds/" | relative_url }}).
- Debt is valued at target price (`par`), which is pegged at 1 USD for Dai 1.0
- A minimum acceptable ratio of debt to collateral (`mat`) is set via
  governance and enforced by liquidating unsafe borrowing positions when
  necessary.

The target price is essentially what the system considers to be the USD value of
1 Dai and is the rate at which the value of all debt and collateral is compared.

- `pip`: USD/ETH - external reference price
- `par`: USD/DAI - target price

The system enforces the target price `par` by using it to derive the DAI/ETH
ration in all comparisons of debt:collateral.

### CDP Safety

Normal CDP operations are only possible when their collateral:debt ratio is
above `mat` - the liquidation ratio.

When checking CDP safety, the external reference price `pip` is used in order to
establish the USD value of the collateral, whilst the target price `par` is
used to price the outsanding debt.

Thus, CDP safety is assessed in USD terms at target price 1 DAI = 1 USD.

By liquidating CDPs that fall below the safe ratio the system can ensure that
the USD value of collateral backing circulating dai remains within determined
parameters.

### Debt market

When buying and selling Dai via `boom` and `bust` the external reference price
`pip` is used to value the collateral being exchanged, whilst the target price
`par` is used to value debt.

Thus the quantity of dai to collateral exchanged is determined in terms of USD
where 1 Dai = 1 USD.

### Global settlement

The system can be globally settled at any time via governance by an operation
known as `cage`. This is roughly equivalent to biting all CDP's at once,
locking the system, and allowing all circulating dai to be exchanged for
collateral at the cage price.

The system uses the external reference price `pip` and the target price `par`
to fix the Dai value of the collateral at the point of cage.

Ultimately, it's the threat of global settlement which provides the incentive
for markets to tend towards the target price of Dai.

### Target Rate Feedback Mechanism

The target price `par` is provided via an updatable price feed, [vox]({{
"dai/1/api/vox" | relative_url }}). It is pegged to 1 USD in Dai 1.0 but could
be updated via TRFM in future versions, allowing the target rate to be
automatically adjusted in response to emerging market conditions. The `vox`
component is subject to ongoing economic modelling research.
