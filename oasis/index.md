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

TODO make these notes coherent.

The market can be accessed via solidity, python, web3 and and a front-end is
available at [oasisdex.com](https://oasisdex.com),

Access to Maker CDPs allows Oasis users to buil their own collateral to build
leveraged trading positions

Oasis direct provides compound operations in a single operation.
bundles multiple operations together
eventually bringing in Maker CDP functionality for leverage on Oasis

Oasis Direct provides integrated Maker CDP functionality for

A front-end to the leverage market is available at
[oasis.direct](https://oasis.direct)

##### OasisDEX

A full-featured, fully on-chain exchange

TODO - descriptive overview

- Front-end
  - [oasisdex.com](https://oasisdex.com)
  - [github](https://github.com/OasisDEX/oasis)
- Solidity Contracts
  - [Simple Market]({{ "oasis/contracts/simple-market" | relative_url }})
  - [Matching Market]({{ "oasis/contracts/matching-market" | relative_url }})

##### OasisDirect

Leveraged positions with Maker + Oasis.

- Front-end
  - [oasis.direct](https://oasis.direct)
  - [github](https://github.com/OasisDEX/oasis-direct-base)
- Solidity Contracts
  - [Oasis Direct Proxy]({{ "oasis/contracts/oasis-direct-proxy" | relative_url }})

##### REST API

Public read-only access to Oasis markets data is available over http via our
[REST API]({{ "oasis/api/1/" | relative_url }}).
