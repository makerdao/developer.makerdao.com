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
ADM=0x9eF05f7F6deB616fd37aC3c959a2dDD25A54E4F5
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

Deployment on Wed 3 Jan 16:06:26 2018

```
GEM=0xd0a1e359811322d97991e03f863a0c30c2cf029c
GOV=0xaaf64bfcc32d0f15873a02163e7e500671a4ffcd
PIP=0xa944bd4b25c9f186a846fd5668941aa3d3b8425f
PEP=0x02998f73fabb52282664094b0ff87741a1ce9030
PIT=0xbd747742b0f1f9791d3e6b85f8797a0cf4fbf10b
ADM=0x74d41fd874234d9bea31ff6b090ba1d0b9dc8785
SAI=0xc4375b7de8af5a38a93548eb8453a498222c4ff2
SIN=0xdcdca4371befceafa069ca1e2afd8b925b69e57b
SKR=0xf4d791139ce033ad35db2b2201435fad668b1b64
DAD=0x6a884c7af48e29a20be9ff04bdde112b5596fcee
MOM=0x72ee9496b0867dfe5e8b280254da55e51e34d27b
VOX=0xbb4339c0ab5b1d9f14bd6e3426444a1e9d86a1d9
TUB=0xa71937147b55deb8a530c7229c442fd3f31b7db2
TAP=0xc936749d2d0139174ee0271bd28325074fdbc654
TOP=0x5f00393547561da3030ebf30e52f5dc0d5d3362c
```
