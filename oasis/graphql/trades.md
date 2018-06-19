---
layout: oasis/graphql
title: Oasis Query API - Trades
---

#### Oasis Trades

Full trade history.

###### Types

```graphql
type OasisTrade {
  offerId:  Int        # Offer identifier
  pairHash: String     # Trading pair hash
  pair:     String     # Trading pair
  maker:    String     # Offer creator address
  taker:    String     # Trade creator address (msg.sender)
  lotGem:   String     # Lot token address
  lotTkn:   String     # Lot token symbol
  lotAmt:   Float      # Lot amount given by maker
  bidGem:   String     # Bid token address
  bidTkn:   String     # Bid token symbol
  bidAmt:   Float      # Bid amount matched by taker
  price:    Float      # bid/lot price
  block:    Int        # Block height
  time:     Datetime   # Block timestamp
  tx:       String     # Transaction hash
  offer:    OasisOffer
}
```

###### Queries

```
type Query {

   # Reads and enables pagination through a set of `OasisTrade`.
   #
   # Arguments
   # first: Only read the first `n` values # of the set.
   # last: Only read the last `n` values # of the set.
   # offset: Skip the first `n` values from our `after`
   # cursor, an alternative to cursor based pagination. May
   # not be used with `last`.
   # before: Read all values in the set
   # before (above) this cursor.
   # after: Read all values in the set
   # after (below) this cursor.
   # orderBy: The method to use when ordering `OasisTrade`.
   # condition: A condition to be used in determining which
   # values should be returned by the collection.
   # filter: A filter to be used in determining
   # which values should be returned by the collection.
   allOasisTrades(
     first: Int,
     last: Int,
     offset: Int,
     before: Cursor,
     after: Cursor,
     orderBy: OasisTradesOrderBy,
     condition: OasisTradeCondition,
     filter: OasisTradeFilter
   ): OasisTradesConnection

}
```

###### Example

Query buys from `0x0005ABcBB9533Cf6F9370505ffeF25393E0D2852` on the `WETH/DAI` pair:

```graphql
query {
  allOasisTrades(
    first: 2,
    condition: {
      pair: "WETH/DAI",
      taker: "0x0005ABcBB9533Cf6F9370505ffeF25393E0D2852"
    }
    orderBy: BLOCK_DESC
  ) {
    totalCount
    nodes {
      offerId
      maker
      taker
      lotTkn
      lotAmt
      bidTkn
      bidAmt
      price
      block
      time
      tx
    }
  }
}
```

```json
{
  "data": {
    "allOasisTrades": {
      "totalCount": 242,
      "nodes": [
        {
          "offerId": 31785,
          "maker": "0x4A16eCf42D72528264B8313b604493eaFef5D845",
          "taker": "0x0005ABcBB9533Cf6F9370505ffeF25393E0D2852",
          "lotTkn": "WETH",
          "lotAmt": "38.349901493390284000",
          "bidTkn": "DAI",
          "bidAmt": "20325.447791496850000000",
          "price": "529.999999999999986441",
          "block": 5279967,
          "time": "2018-03-18T23:15:00+00:00",
          "tx": "0x97642ce2a16e90cedc50b126a30e1e1e42bfbbb8e5410ba0fd81cbc9434eba04"
        },
        {
          "offerId": 31773,
          "maker": "0x4A16eCf42D72528264B8313b604493eaFef5D845",
          "taker": "0x0005ABcBB9533Cf6F9370505ffeF25393E0D2852",
          "lotTkn": "WETH",
          "lotAmt": "33.861028908660295000",
          "bidTkn": "DAI",
          "bidAmt": "17777.040177046656000000",
          "price": "525.000000000000033224",
          "block": 5279958,
          "time": "2018-03-18T23:13:40+00:00",
          "tx": "0x96b2822905b746405c41d09536ee001a27e39e2c7d121fe1266523193e832206"
        }
      ]
    }
  }
}
```
