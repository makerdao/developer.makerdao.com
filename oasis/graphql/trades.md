---
layout: oasis/graphql
title: Oasis Query API - Trades
---

### Oasis Trades

Full trade history.

An `OasisTrade` represents a transaction submitted by `msg.sender` (the
`taker`) to match some portion of an `OasisOffer`.  When a trade occurs,
`lotAmt` of ERC20 `lotGem` is moved from Oasis to `taker` whilst `bidAmt` of
ERC20 `bidGem` is moved from the `taker` to the `maker`.

```graphql
type OasisTrade {
  offerId:  Int        # Offer identifier
  market:   String     # Market base/quote symbol
  act:      String     # Market action (buy|sell)
  pair:     String     # Trading pair hash
  maker:    String     # Offer creator address
  taker:    String     # Trade creator address (msg.sender)
  lotGem:   String     # Lot token address
  lotTkn:   String     # Lot token symbol
  lotAmt:   Float      # Lot amount given by maker
  bidGem:   String     # Bid token address
  bidTkn:   String     # Bid token symbol
  bidAmt:   Float      # Bid amount matched by taker
  price:    Float      # Market price (quote)
  block:    Int        # Block height
  time:     Datetime   # Block timestamp
  tx:       String     # Transaction hash
  offer:    OasisOffer
}
```

```graphql
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

#### Example

Query trades from `0x0005ABcBB9533Cf6F9370505ffeF25393E0D2852` on the `WETHDAI` market:

```graphql
query {
  allOasisTrades(
    first: 2,
    condition: {
      market: "WETHDAI",
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
      act
      block
      time
      tx
    }
  }
}
```

###### Result

```json
{
  "data": {
    "allOasisTrades": {
      "totalCount": 579,
      "nodes": [
        {
          "offerId": 75463,
          "maker": "0xE5A55E40cf41Af9Dd463E16CEc9e299E52Be7e0E",
          "taker": "0x0005ABcBB9533Cf6F9370505ffeF25393E0D2852",
          "lotTkn": "DAI",
          "lotAmt": "6243.744408617758000000",
          "bidTkn": "WETH",
          "bidAmt": "11.456411758931667000",
          "price": "544.999999999999955047",
          "act": "buy",
          "block": 5817091,
          "time": "2018-06-19T14:00:43+00:00",
          "tx": "0x0b90b2c84446afefc602db621f7bedda891515bbccdbb5438635178d840af6dd"
        },
        {
          "offerId": 75463,
          "maker": "0xE5A55E40cf41Af9Dd463E16CEc9e299E52Be7e0E",
          "taker": "0x0005ABcBB9533Cf6F9370505ffeF25393E0D2852",
          "lotTkn": "DAI",
          "lotAmt": "13047.840000000000000000",
          "bidTkn": "WETH",
          "bidAmt": "23.940990825688072000",
          "price": "545.000000000000031745",
          "act": "buy",
          "block": 5817089,
          "time": "2018-06-19T14:00:21+00:00",
          "tx": "0xe618927578c58346db40ed18d3510ef97724315319f061b0a2c542e53f50bb07"
        }
      ]
    }
  }
}
```
