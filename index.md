---
layout: home
title: Developer
---

## Trade
<p class="lead">Trade with OasisDEX - our decentralized exchange. </p>

A fully on-chain ERC20 exchange, with leverage by Maker.

[Oasis]({{ "oasis/" | relative_url }})

## Borrow
<p class="lead">Deposit collateral to access Dai-denominated credit.</p>

Autonomous borrowing - borrow Dai by locking up ETH in the Maker collateral
vault.

Example:

1. Lock up 100ETH in the collateral vault
2. Borrow up to 50ETH worth of Dai
3. Repay borrowed Dai at any time and get your collateral back

TODO write a short use-case section demonstrating borrowing/expand the intro
borrowing section?

[Learn more]({{ "dai/1/" | relative_url }})

## Earn
<p class="lead">Pool collateral and earn a return.</p>

When the system is healthy, PETH is expected to increase in value over time
relative to ETH, providing a return to collateral holders.

- TODO decide if the collateral pool is something we want to emphasise?

[Learn more]({{ "dai/1/pool" | relative_url }})

## Arbitrage
<p class="lead">Compete for profit opportunities provided by the Maker platform.</p>

- Maker creates a market for debt by buying and selling dai as the liquidator
  vault goes in and out of surplus.
- PETH supply is adjusted to maintain its ratio to collateral proportional to
  circulating dai
- Opportunities for arbitrage across DAI - PETH - USD pairs.

[Keepers]({{ "keepers/" | relative_url }})
[Boom & Bust]({{ "dai/1/api/tap" | relative_url }})

## Leverage
<p class="lead">Re-invest borrowed Dai to build leveraged positions.</p>


Making an ERC20 token containing a CDP, which would kind of be like a leveraged
ETH token (think leveraged ETFs on NASDAQ), is something that has been
discussed.

1. Basic Example

TODO

2. Oasis Direct

TODO

3. Roll your own

It would be easy to write a contract that accepts ETH and gives you back a
recursively leveraged CDP

## Hedge
<p class="lead">Dai stablility.</p>

Buy dai as a shelter from volatility. Move value into dai during a periods of uncertainty.

[Stability]({{ "dai/1/stability" | relative_url }})
[Dai Users]({{ "dai/1/" | relative_url }})
