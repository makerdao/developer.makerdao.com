---
layout: oasis/graphql
title: Oasis Query API - Offers
---

### Oasis Offers

Full offer history.

An `OasisOffer` represents a transaction submitted by `msg.sender` (the
`maker`) to sell `lotAmt` of ERC20 `lotGem` for `bidAmt` of ERC20 `bidGem`.
When an offer is submitted the `lot` is moved from the `maker` to Oasis.

```graphql
type OasisOffer {
  id:       Int        # Unique offer identifier
  market:   String     # Market base/quote symbol
  act:      String     # Market action (ask|bid)
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
  filled:   Boolean    # true of the offer has been fully executed
  killed:   Int        # 0 if the offer is live or block height when killed
  block:    Int        # Block height
  time:     Datetime   # Block timestamp
  tx:       String     # Transaction hash
  trades:   [OasisTrades]
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
   allOasisOffers(
     first: Int,
     last: Int,
     offset: Int,
     before: Cursor,
     after: Cursor,
     orderBy: OasisOffersOrderBy,
     condition: OasisOfferCondition,
     filter: OasisOfferFilter
   ): OasisOffersConnection

}
```

#### Example

Query offers from `0x0005ABcBB9533Cf6F9370505ffeF25393E0D2852` on the `WETHDAI` market:

```graphql
query {
  allOasisOffers(
    first: 2,
    condition: {
      market: "WETHDAI",
      maker: "0x0005ABcBB9533Cf6F9370505ffeF25393E0D2852"
    }
    orderBy: BLOCK_DESC
  ) {
    totalCount
    nodes {
      id
      maker
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
    "allOasisOffers": {
      "totalCount": 16187,
      "nodes": [
        {
          "id": 76105,
          "maker": "0x0005ABcBB9533Cf6F9370505ffeF25393E0D2852",
          "lotTkn": "WETH",
          "lotAmt": "9.577846307710560000",
          "bidTkn": "DAI",
          "bidAmt": "5098.358465657008000000",
          "price": "532.307399999999984741",
          "act": "ask",
          "block": 5829608,
          "time": "2018-06-21T17:29:30+00:00",
          "tx": "0x40def45425295c286cbcfc9bbc8593ccd66bf670cc81f5ccba726be35289162b"
        },
        {
          "id": 76104,
          "maker": "0x0005ABcBB9533Cf6F9370505ffeF25393E0D2852",
          "lotTkn": "WETH",
          "lotAmt": "14.422153692289440000",
          "bidTkn": "DAI",
          "bidAmt": "7686.581022240980000000",
          "price": "532.970400000000017156",
          "act": "ask",
          "block": 5829588,
          "time": "2018-06-21T17:24:34+00:00",
          "tx": "0x20cf5765c8fce7ee4ecf16fbf302f89376ca32cef4a62187e661d8f5285e406b"
        }
      ]
    }
  }
}
```
