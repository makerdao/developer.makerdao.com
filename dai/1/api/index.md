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

##### Tokens

- `gem`: underlying collateral (ether, in practice)
- `dai`: stablecoin
- `peth`: abstracted collateral claim
- `sin`: anticoin, dai mirror

##### Core components

- `vox`: target price feed
- `tub`: [CDP]({{ "dai/1/api/tub" | relative_url }}) record store
- `tap`: [liquidation mechanism]({{ "dai/1/api/tap" | relative_url }})
- `top`: [global settlement]({{ "dai/1/api/top" | relative_url }}) facilitator

##### Risk parameters

Configured via governance:

- `way`: Dai reference price drift
- `hat`: Debt ceiling
- `mat`: Liquidation ratio
- `tax`: Stability fee
- `axe`: Liquidation penalty
- `gap`: Join/Exit and Boom/Bust spread
