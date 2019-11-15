---
layout: oasis/default
title: Oasis
---

### Oasis

<p class="lead">
  Decentralized ERC20 exchange with borrowing & leverage by Maker
</p>

_Announcement: On Monday 18th of November 2019 at 10am UTC we are going to rename DAI markets to SAI markets on our APIs (both RestAPI and GraphQL)._

_Later that day, after 4pm UTC, we are gonna reintroduce DAI markets but DAI will point to new MultiCollateral DAI token._

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
