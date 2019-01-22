---
layout: home
title: Developer
---

## Borrow
<p class="lead">Deposit collateral to access Dai-denominated credit.</p>

Autonomous borrowing - borrow Dai by locking up ETH in the Maker collateral
vault.

Example:

1. Lock up 100ETH in the collateral vault
2. Borrow up to 66ETH worth of Dai
3. Repay borrowed Dai at any time in the future and get your collateral back

[Learn more]({{ "dai/1/" | relative_url }})

## Arbitrage
<p class="lead">Compete for profit opportunities provided by the Maker platform.</p>

* Maker creates a market for debt by buying and selling Dai as the liquidator
  vault goes in and out of surplus.
* PETH supply is adjusted to maintain its ratio to collateral proportional to
  circulating Dai.

Opportunities for arbitrage across DAI - PETH - USD pairs.

[Learn more]({{ "dai/1/api/tap" | relative_url }})

## Leverage
<p class="lead">Re-invest borrowed Dai to build leveraged positions.</p>

[CDP]({{ "dai/1/api/tub" | relative_url }}) owners can use borrowed Dai to
purchase more collateral on the open market, and then use that collateral to
open another CDP, thus increasing exposure to changes in the value of the
collateral.

This functionality is being used by the [proxy contracts]({{ "oasis/contracts"
| relative_url }}) supporting [Oasis Direct](https://oasis.direct) for example,
and it's easy to imagine how these properties can be used in interesting ways.

It would be easy for example imagine to writing a contract that accepts ETH and
gives you back a recursively-leveraged CDP or an ERC20 token containing a CDP,
which would resemble a leveraged ETH token (think leveraged ETFs on NASDAQ).

## Hedge
<p class="lead">Manage risk with Dai.</p>

Buy Dai as a shelter from volatility. Exchange crypto-assets for Dai during
periods of uncertainty.

[Learn more]({{ "dai/1/stability" | relative_url }})
