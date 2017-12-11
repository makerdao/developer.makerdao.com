---
layout: home
title: Developer
---

## Trade
<p class="lead">Trade with OasisDEX - our decentralized exchange. </p>

A fully on-chain ERC20 exchange, with leverage by Maker.

[Learn more]({{ "oasis/" | relative_url }})

## Borrow
<p class="lead">Deposit collateral to access Dai-denominated credit.</p>

Autonomous borrowing - borrow Dai by locking up ETH in the Maker collateral
vault.

Example:

1. Lock up 100ETH in the collateral vault
2. Borrow up to 50ETH worth of Dai
3. Repay borrowed Dai at any time in the future and get your collateral back

[Learn more]({{ "dai/1/" | relative_url }})

## Earn
<p class="lead">Pool collateral and earn a return.</p>

When the system is healthy, PETH is expected to increase in value over time
relative to ETH, providing a return to collateral holders.

[Learn more]({{ "dai/1/api/pool" | relative_url }})

## Arbitrage
<p class="lead">Compete for profit opportunities provided by the Maker platform.</p>

* Maker creates a market for debt by buying and selling dai as the liquidator vault goes in and out of surplus.
* PETH supply is adjusted to maintain its ratio to collateral proportional to circulating dai.

Opportunities for arbitrage across DAI - PETH - USD pairs.

[Learn more]({{ "dai/1/api/tap" | relative_url }})

## Leverage
<p class="lead">Re-invest borrowed Dai to build leveraged positions.</p>

[CDP]({{ "dai/1/api/tub" | relative_url }}) owners can use borrowed dai to
purchase more collateral on the open market, and then use that collateral to
open another CDP, thus increasing exposure to changes in the value of the
collateral.

This functionality is being used by the [proxy contracts]({{ "oasis/contracts"
| relative_url }}) supporting [oasis.direct](https://oasis.direct) for example
and it's easy to imagine how these properties be used in interesting ways.

It would easy for example imagine to write a contract that accepts ETH and gives you back a
recursively leveraged CDP. Or an ERC20 token containing a CDP, which would kind
of be like a leveraged ETH token (think leveraged ETFs on NASDAQ).

## Hedge
<p class="lead">Dai stablility.</p>

Buy dai as a shelter from volatility. Move value into dai during a periods of uncertainty.

[Learn more]({{ "dai/1/stability" | relative_url }})
