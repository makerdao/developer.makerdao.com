---
layout: oasis/graphql
title: Oasis Query API - Markets
---

### Oasis Markets

List all traded markets.

Period is an interval over which aggregated fields are computed. Defaults to
`period: '24 hours'` - the last 24 hours of trading.

Price is volume weighted over the given `period`.

```graphql
type OasisMarket {
  id:      String # market symbol e.g MKRDAI
  base:    String # base symbol   e.g MKR
  quote:   String # quote symbol  e.g DAI
  buyVol:  Float  # total buy volume (base)
  sellVol: Float  # total sell volume (base)
  price:   Float  # volume weighted price (quote)
  high:    Float  # max sell price
  low:     Float  # min buy price
}
```

```graphql
type Query {

  oasisMarkets(period: String): [OasisMarket]

}
```

#### Example

Query markets data for the last week:

```graphql
{
  oasisMarkets(period: "1 week") {
    nodes {
      id
      base
      quote
      buyVol
      sellVol
      price
      high
      low
    }
  }
}
```

###### Result

```json
{
  "data": {
    "oasisMarkets": {
      "nodes": [
        {
          "id": "MKRDAI",
          "base": "MKR",
          "quote": "DAI",
          "buyVol": "72.725497799769026772",
          "sellVol": "74.753946931260026454",
          "price": "554.637094254068637259388160179376039628",
          "high": "627.690371518941404336",
          "low": "400.000000000000000000"
        },
        {
          "id": "MKRWETH",
          "base": "MKR",
          "quote": "WETH",
          "buyVol": "206.121945907526152150",
          "sellVol": "120.132512911876681168",
          "price": "1.09879361952161937154424520693056543727",
          "high": "1.240000000000000103",
          "low": "1.00000000000000000000"
        },
        {
          "id": "WETHDAI",
          "base": "WETH",
          "quote": "DAI",
          "buyVol": "2502.259304279893017492",
          "sellVol": "2342.374954102770721191",
          "price": "514.668034747466295537469331654062359477",
          "high": "554.704800000000009647",
          "low": "475.000000000000000000"
        }
      ]
    }
  }
}
```
