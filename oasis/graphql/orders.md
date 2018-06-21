---
layout: oasis/graphql
title: Oasis Query API - Orderbook
---

### Oasis Orders

List all live offers.

Orders are unfilled OasisOffers presented in orderbook style.

```graphql
type OasisOrder {
  offerId: Int    # Offer Id
  market:  String # Market symbol (base/quote)
  price:   Float  # Offer price (quote)
  amount:  Float  # Offer amount (base)
  act:     String # Action (ask|bid)
}
```
#### Example

Fetch bids and asks for the MKRDAI market:

```graphql
{
  allOasisOrders(condition: { market: "MKRDAI" }) {
    totalCount
    nodes {
      market
      offerId
      price
      amount
      act
    }
  }
}
```

###### Result

```json
{
  "data": {
    "allOasisOrders": {
      "totalCount": 34,
      "nodes": [
        {
          "market": "MKRDAI",
          "offerId": 76126,
          "price": "578.518714103990236338",
          "amount": "1.042493748812877000",
          "act": "ask"
        },
        {
          "market": "MKRDAI",
          "offerId": 75980,
          "price": "588.321828466784850000",
          "amount": "0.957506251187123110",
          "act": "ask"
        },
        {
          "market": "MKRDAI",
          "offerId": 74120,
          "price": "597.000000000000000000",
          "amount": "25.294295629195980000",
          "act": "ask"
        },
        {
          "market": "MKRDAI",
          "offerId": 74318,
          "price": "600.000000000000000000",
          "amount": "4.000000000000000000",
          "act": "ask"
        },
        {
          "market": "MKRDAI",
          "offerId": 75709,
          "price": "603.216747385151000000",
          "amount": "8.000000000000000000",
          "act": "ask"
        },
        {
          "market": "MKRDAI",
          "offerId": 74040,
          "price": "625.000000000000000000",
          "amount": "37.000000000000000000",
          "act": "ask"
        },
        {
          "market": "MKRDAI",
          "offerId": 52880,
          "price": "1140.000000000000000000",
          "amount": "4.605263157894736840",
          "act": "ask"
        },
        {
          "market": "MKRDAI",
          "offerId": 52879,
          "price": "1145.000000000000000000",
          "amount": "5.000000000000000000",
          "act": "ask"
        },
        {
          "market": "MKRDAI",
          "offerId": 52878,
          "price": "1150.000000000000000000",
          "amount": "10.000000000000000000",
          "act": "ask"
        },
        {
          "market": "MKRDAI",
          "offerId": 52143,
          "price": "1155.000000000000000000",
          "amount": "59.470129870558440892",
          "act": "ask"
        },
        {
          "market": "MKRDAI",
          "offerId": 44221,
          "price": "1200.000000000000000000",
          "amount": "10.000000000000000000",
          "act": "ask"
        },
        {
          "market": "MKRDAI",
          "offerId": 21293,
          "price": "1222.000000000000000000",
          "amount": "1.516423131751227500",
          "act": "ask"
        },
        {
          "market": "MKRDAI",
          "offerId": 44886,
          "price": "1300.000000000000000000",
          "amount": "10.000000000000000000",
          "act": "ask"
        },
        {
          "market": "MKRDAI",
          "offerId": 44889,
          "price": "1400.000000000000000000",
          "amount": "10.000000000000000000",
          "act": "ask"
        },
        {
          "market": "MKRDAI",
          "offerId": 44891,
          "price": "1500.000000000000000000",
          "amount": "10.000000000000000000",
          "act": "ask"
        },
        {
          "market": "MKRDAI",
          "offerId": 689,
          "price": "1750.000000000000000000",
          "amount": "34.960000000000000000",
          "act": "ask"
        },
        {
          "market": "MKRDAI",
          "offerId": 16055,
          "price": "17700.000000000000000000",
          "amount": "8.888000000000000000",
          "act": "ask"
        },
        {
          "market": "MKRDAI",
          "offerId": 16054,
          "price": "211.000000000000000000",
          "amount": "100.000000000000000000",
          "act": "bid"
        },
        {
          "market": "MKRDAI",
          "offerId": 31573,
          "price": "280.000000000000000000",
          "amount": "10.000000000000000000",
          "act": "bid"
        },
        {
          "market": "MKRDAI",
          "offerId": 31572,
          "price": "310.000000000000000000",
          "amount": "10.000000000000000000",
          "act": "bid"
        },
        {
          "market": "MKRDAI",
          "offerId": 31570,
          "price": "340.000000000000000000",
          "amount": "10.000000000000000000",
          "act": "bid"
        },
        {
          "market": "MKRDAI",
          "offerId": 31567,
          "price": "370.000000000000000000",
          "amount": "10.000000000000000000",
          "act": "bid"
        },
        {
          "market": "MKRDAI",
          "offerId": 75379,
          "price": "405.000000000000000000",
          "amount": "1.000000000000000000",
          "act": "bid"
        },
        {
          "market": "MKRDAI",
          "offerId": 75197,
          "price": "441.000000000000000000",
          "amount": "11.500000000000000000",
          "act": "bid"
        },
        {
          "market": "MKRDAI",
          "offerId": 75642,
          "price": "450.010100000000000000",
          "amount": "1.000000000000000000",
          "act": "bid"
        },
        {
          "market": "MKRDAI",
          "offerId": 75693,
          "price": "480.000000000000000000",
          "amount": "0.500000000000000000",
          "act": "bid"
        },
        {
          "market": "MKRDAI",
          "offerId": 75755,
          "price": "501.000000000000000000",
          "amount": "46.000000000000000000",
          "act": "bid"
        },
        {
          "market": "MKRDAI",
          "offerId": 76094,
          "price": "515.331968314432044013",
          "amount": "12.419179079717042000",
          "act": "bid"
        },
        {
          "market": "MKRDAI",
          "offerId": 75656,
          "price": "516.624800000000060020",
          "amount": "0.182395236723549700",
          "act": "bid"
        },
        {
          "market": "MKRDAI",
          "offerId": 75910,
          "price": "529.422298776867977750",
          "amount": "9.066486264536854000",
          "act": "bid"
        },
        {
          "market": "MKRDAI",
          "offerId": 75651,
          "price": "530.096645857875426690",
          "amount": "3.018317532288210500",
          "act": "bid"
        },
        {
          "market": "MKRDAI",
          "offerId": 76123,
          "price": "544.123628796756730054",
          "amount": "2.940508214168435800",
          "act": "bid"
        },
        {
          "market": "MKRDAI",
          "offerId": 76140,
          "price": "544.124000000000000000",
          "amount": "1.000000000000000000",
          "act": "bid"
        },
        {
          "market": "MKRDAI",
          "offerId": 75803,
          "price": "549.999999999999982400",
          "amount": "0.045454545454545456",
          "act": "bid"
        }
      ]
    }
  }
}
```
