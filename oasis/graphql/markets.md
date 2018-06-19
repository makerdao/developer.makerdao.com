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
  pair:   String # e.g MKR/DAI
  lotGem: String # base gem address
  bidGem: String # quote gem address
  vol:    Float  # volume
  price:  Float  # volume weighted price
  low:    Float  # min price
  high:   Float  # max price
}
```

```graphql
type Query {

  oasisMarkets(period: String): {
    nodes: [OasisMarket]
    pageInfo: PageInfo!
    totalCount: Int
  }

}
```

#### Example

Query markets data for the last week:

```graphql
{
  oasisMarkets(period: "1 week") {
    nodes {
      pair
      lotGem
      bidGem
      vol
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
          "pair": "DAI/MKR",
          "lotGem": "0x89d24A6b4CcB1B6fAA2625fE562bDD9a23260359",
          "bidGem": "0x9f8F72aA9304c8B593d555F12eF6589cC3A579A2",
          "vol": "32075.875311560017900000",
          "price": "0.00192300456430088513087069712478938580",
          "high": "0.00232558139534883721",
          "low": "0.00148148148148148148"
        },
        {
          "pair": "WETH/MKR",
          "lotGem": "0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2",
          "bidGem": "0x9f8F72aA9304c8B593d555F12eF6589cC3A579A2",
          "vol": "311.309393794458086310",
          "price": "0.84056132067046168932859920389368236150",
          "high": "0.95238095238095245569",
          "low": "0.76881522520222800000"
        },
        {
          "pair": "WETH/DAI",
          "lotGem": "0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2",
          "bidGem": "0x89d24A6b4CcB1B6fAA2625fE562bDD9a23260359",
          "vol": "2415.185039968458593493",
          "price": "500.253972925353388102830979211526755518",
          "high": "540.126000000000038311",
          "low": "459.488416800000000000"
        },
        {
          "pair": "MKR/WETH",
          "lotGem": "0x9f8F72aA9304c8B593d555F12eF6589cC3A579A2",
          "bidGem": "0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2",
          "vol": "163.438587869086320628",
          "price": "1.17510996335206317514332023523546215180",
          "high": "1.303000000000000079",
          "low": "1.051292394557801712"
        },
        {
          "pair": "DAI/WETH",
          "lotGem": "0x89d24A6b4CcB1B6fAA2625fE562bDD9a23260359",
          "bidGem": "0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2",
          "vol": "2476778.624484158688811458",
          "price": "0.00206154417006211140255911891671184397",
          "high": "0.00218818380743982498",
          "low": "0.00188185815541425862"
        },
        {
          "pair": "MKR/DAI",
          "lotGem": "0x9f8F72aA9304c8B593d555F12eF6589cC3A579A2",
          "bidGem": "0x89d24A6b4CcB1B6fAA2625fE562bDD9a23260359",
          "vol": "140.965084194817052630",
          "price": "596.410255176371917473894089622605594944",
          "high": "675.408945031372548353",
          "low": "546.673820718150000000"
        },
        {
          "pair": "WETH/RHOC",
          "lotGem": "0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2",
          "bidGem": "0x168296bb09e24A88805CB9c33356536B980D3fC5",
          "vol": "16.837200459956799999",
          "price": "458.466253436490750399529887392079090657",
          "high": "500.000000000000000000",
          "low": "438.596491230000000000"
        },
        {
          "pair": "RHOC/WETH",
          "lotGem": "0x168296bb09e24A88805CB9c33356536B980D3fC5",
          "bidGem": "0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2",
          "vol": "3024.788036610000000000",
          "price": "0.00231255372324967237909506304477888846",
          "high": "0.00232999999998724800",
          "low": "0.00230000000246472906"
        }
      ]
    }
  }
}
```
