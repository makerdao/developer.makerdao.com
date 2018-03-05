---
layout: dai/api
title: Dai
subtitle: API
---

### Core System

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

- `vox`: [target price]({{ "dai/1/api/vox" | relative_url }}) feed
- `tub`: [CDP]({{ "dai/1/api/tub" | relative_url }}) record store
- `tap`: [liquidation mechanism]({{ "dai/1/api/tap" | relative_url }})
- `top`: [global settlement]({{ "dai/1/api/top" | relative_url }}) facilitator

##### Risk parameters

Configured via governance:

- `way`: Dai reference price drift
- `cap`: Debt ceiling
- `mat`: Liquidation ratio
- `tax`: Stability fee
- `axe`: Liquidation penalty
- `gap`: Join/Exit and Boom/Bust spread

##### Deployments

Token mappings:

- DAI: `SAI`
- MKR: `GOV`
- WETH: `GEM`
- PETH: `SKR`

Mainnet:

Deployment on ethlive Mon 18 Dec 03:12:57 GMT 2017

```bash
GEM=0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2
GOV=0x9f8F72aA9304c8B593d555F12eF6589cC3A579A2
PIP=0x729D19f657BD0614b4985Cf1D82531c67569197B
PEP=0x99041F808D598B782D5a3e498681C2452A31da08
PIT=0x69076e44a9c70a67d5b79d95795aba299083c275
ADM=0x8e2a84d6ade1e7fffee039a35ef5f19f13057152
SAI=0x89d24a6b4ccb1b6faa2625fe562bdd9a23260359
SIN=0x79f6d0f646706e1261acf0b93dcb864f357d4680
SKR=0xf53ad2c6851052a81b42133467480961b2321c09
DAD=0x315cbb88168396d12e1a255f9cb935408fe80710
MOM=0xf2c5369cffb8ea6284452b0326e326dbfdcb867c
VOX=0x9b0f70df76165442ca6092939132bbaea77f2d7a
TUB=0x448a5065aebb8e423f0896e6c5d525c040f59af3
TAP=0xbda109309f9fafa6dd6a9cb9f1df4085b27ee8ef
TOP=0x9b0ccf7c8994e19f39b2b4cf708e0a7df65fa8a3
```

Kovan:

Deployment on Mon 18 Dec 14:14:10 GMT 2017

```bash
GEM=0xd0a1e359811322d97991e03f863a0c30c2cf029c
GOV=0xaaf64bfcc32d0f15873a02163e7e500671a4ffcd
PIP=0xa944bd4b25c9f186a846fd5668941aa3d3b8425f
PEP=0x02998f73fabb52282664094b0ff87741a1ce9030
PIT=0xbd747742b0f1f9791d3e6b85f8797a0cf4fbf10b
ADM=0xac51838ce4de0a7582eaa6d6d28cb4c2dbbf67ab
SAI=0x95878488a599e1d821c0ff2bc079b9e7f96d95be
SIN=0x51a66da43f7bd7233d00428953cd0c36f4cf652a
SKR=0x1508d42373235103081bd4d223379469f686bc55
DAD=0x8ee52ba655729b88f6274c99395fc3660be2c36d
MOM=0x8a70c067ab9b7cbde31527874fcafe7c39fe1197
VOX=0x9ac2c143257018369691a6eb3ca2150ef7309b27
TUB=0xa6bfc88aa5a5981a958f9bcb885fcb3db0bf941e
TAP=0x03113ba1eb4bb193d916d8345ef20bc5f209438c
TOP=0x0c6476699309f166f3a7188f57f3648dc3d07e7d
```
