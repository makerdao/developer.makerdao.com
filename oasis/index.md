---
layout: oasis/default
title: Oasis
---

### Oasis

Oasis is:

- decentralized ERC20 Exchange on the Ethereum blockchain
- with decentralized borrowing & leverage by Maker

Oasis components:

##### OasisDEX

A full-featured, fully on-chain exchange

- Front-end
  - [oasisdex.com](https://oasisdex.com)
  - [codebase](https://github.com/OasisDEX/oasis)
- Solidity Contracts
  - [Simple Market]({{ "oasis/contracts/simple-market" | relative_url }})
  - [Matching Market]({{ "oasis/contracts/matching-market" | relative_url }})

##### OasisDirect

Leveraged positions with Maker + Oasis.

- Front-end
  - [direct.oasisdex.com](https://direct.oasisdex.com)
  - [codebase](https://github.com/OasisDEX/oasis-direct-base)
- Solidity Contracts
  - [Oasis Direct Proxy]({{ "oasis/contracts/oasis-direct-proxy" | relative_url }})

##### REST API

Public read-only access to Oasis markets data is available over http via our
[REST API]({{ "api/1/" | relative_url }}).
