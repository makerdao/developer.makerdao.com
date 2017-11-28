---
layout: dai/api
title: Dai
subtitle: API
---

## Overview

Dai 1.0 is a simplification of the Dai Stablecoin System intended for field
testing and refining Dai components. Dai 1.0 has several features that
distinguish it from future versions:

- trusted price feed
- single collateral type
- liquidations at fixed price (rather than auctions)

This API documentation is an introduction to Dai, aimed at those seeking an
understanding of the Solidity implementation. We assume knowledge of the [white
paper], a high level overview of Dai. A reading of the [purple paper], the (in
progress) detailed Dai technical specification and reference implementation, is
strongly encouraged but not required.

[white paper]: https://github.com/makerdao/docs/blob/master/Dai.md
[purple paper]: https://makerdao.com/purple

Dai uses the following tokens:

- `gem`: underlying collateral (ether, in practice)
- `dai`: stablecoin
- `peth`: abstracted collateral claim

Dai has the following core components:

- `vox`: target price feed
- `tub`: CDP record store
- `tap`: liquidation mechanism
- `top`: global settlement facilitator

Dai is configured by the following 'risk parameters' (via governance):

- `way`: Dai reference price drift
- `hat`: Debt ceiling
- `mat`: Liquidation ratio
- `tax`: Stability fee
- `axe`: Liquidation penalty
- `gap`: Join/Exit and Boom/Bust spread

#### Target Price Feed

The `vox` provides the Dai *target price*, given in terms of the reference
unit, by `par`. For example, `par == 2` with USD as the reference unit implies
a target price of 2 USD per Sai.

The target price can vary in time, at a rate given by `way`, which is the
multiplicative rate of change per second.

In Dai 1.0 the sensitivity, `how`, is set to zero. Adjustments to the target
price are made by adjusting the rate of change, `way`, directly with `coax`.
In future iterations, `how` may be non-zero and `way` adjustments will then
follow automatically via the feedback mechanism. The `vox` component is
subject to ongoing economic modelling research.
