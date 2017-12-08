---
layout: oasis/contracts
title: Oasis Contracts
---

### Simple Market

A simple open orderbook market. Enables orders to be added to the pool and
allows anyone to take a specified quantity of an order. Cancelled orders are
refunded to the maker.

* [simple-market.sol](https://github.com/makerdao/maker-otc/blob/master/src/simple_market.sol)
* [Deployed contract]() (Etherscan)

##### Offer

Alias: `make`

Put an order onto the books. Transfers funds from the caller to Oasis.

```js
function offer(uint wad, ERC20 gemA, uint jam, ERC20 gemB) returns (bool) { ... }
```

##### Buy

Alias: `take`

Take an order off the books. Transfers funds from the caller to the offer
maker, and from Oasis to the caller.

```js
function buy(uint offer, uint qty) returns (bool) { ... }
```

##### Cancel

Alias: `kill`

Cancel an offer - refunds the maker.


```js
function uint(uint offer) returns (bool success) { ... }
```
