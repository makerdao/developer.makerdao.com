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

##### OasisDex

The market can be accessed via solidity, web3, python, with a
[front-end](https://github.com/OasisDEX/oasis) available at
[oasisdex.com](https://oasisdex.com),

##### OasisDirect

Oasis Direct makes use of proxy contract functionality from
[Dappsys](https://dapp.tools/dappsys) to bundle multiple transactions into a
single call. A [front-end](https://github.com/OasisDEX/oasis-direct-base) at
[oasis.direct](https://oasis.direct) provides simplified access to multi-step
trading operations on Oasis and leverage via Maker.

##### Contracts

[Documentation]({{ "oasis/contracts/" | relative_url }}) for the Solidty Contracts which facilitate trading on Oasis.

##### REST API

Public read-only access to Oasis markets data is available over http via our
[REST API]({{ "oasis/api/1/" | relative_url }}).
