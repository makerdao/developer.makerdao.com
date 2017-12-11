---
layout: oasis/contracts
title: Oasis Contracts
---

### Matching Market

Inherits from Simple Market. Shares the same liquidity pool. Uses` a sorted list
to facilitate order matching.

* [matching-market.sol](https://github.com/makerdao/maker-otc/blob/master/src/matching_market.sol)
* [Deployed contract]() (Etherscan)

##### Offer

Alias: `make`

Simple market offers with sorting and position

```js
function offer(uint wad, ERC20 gemA, uint jam, ERC20 gemB, uint pos) returns (uint) { ... }
```

##### Buy

Alias: `take`

Simple market buys with sorting and position

```js
function buy(uint offer, uint qty) returns (bool) { ... }
```

##### Cancel

Alias: `kill`

Cancel an offer - refunds the maker.


```js
function uint(uint offer) returns (bool success) { ... }
```

##### Insert

Insert an offer into the sorted list


```js
function uint(uint id, uint pos) returns (bool) { ... }
```

TODO

* sellAllAmount
* buyAllAmount
* getBuyAmount
* getPayAmount
