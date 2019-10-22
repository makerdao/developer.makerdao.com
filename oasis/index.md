---
layout: oasis/default
title: Oasis
---

### Oasis

<p class="lead">
  Decentralized ERC20 exchange with borrowing & leverage by Maker
</p>

Oasis is a liquidity pool on the Ethereum blockchain. The Simple Market and
Matching Market smart contracts provide for the trustless atomic exchange of
ERC20 tokens without third party counter-risk.

##### Oasis Trade

The market can be accessed directly from Ethereum or with
the official front-end available at [oasis.app/trade](https://oasis.app/trade).

##### Oasis Trade Instant

Instant trade module makes use of proxy contract functionality from
[Dappsys](https://dapp.tools/dappsys) to bundle multiple transactions into a
single call. The front-end provides simplified access to multi-step
trading operations on Oasis and leverage via Maker.

##### REST API

Public read-only access to Oasis markets data is available over http via our
[REST API v2]({{ "oasis/api/2/" | relative_url }}).
