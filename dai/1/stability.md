---
layout: dai/default
title: Dai stability
---

## Stability

Dai has a number of properties from which it derives stability:

Actually a couple of pieces of price information.

Re-write in that context.

#### Reference price

Dai 1.0 is intended to maintain stability relative to a reference; the US Dollar.

The reference price for collateral, ETHUSD is provided by an external oracle,
which is completely trusted. TODO - link to or describe feeds & medianizer.

#### Debt/Collateral ratio

1. Safety checking

When checking CDP safety the external reference price is used in order to
establish the USD value of the collateral, whilst the target price[^i] is used
to price the oustanding debt.

Thus CDP safety is assesed at target price. 1 DAI = 1 USD.

2. Enforcing the ratio

Forced liquidation when required. Ensures that the system is always
collateralised to a minimum ratio.

#### Debt market

When buying and selling dai via `boom` and `bust` the external reference price
is used to value collateral, whilst the target price is used for dai.

Thus Dai is bought and sold at target price. 1 DAI = 1 USD.

#### TRFM

Target price can be varied if required in order to respond to market price.

#### Global settlement

Same as above. System is settled with collateral valued using the external
reference and the debt at target price.

1 DAI = 1 USD.

Ultimately, it's the threat of global settlement which provides the incentive to tend towards target price.

[^i]: Pegged at 1:1 for launch.
