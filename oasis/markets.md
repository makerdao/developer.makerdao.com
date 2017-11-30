---
layout: oasis/default
title: Oasis Markets API
description: Public rest endpoints for markets data
apiRoot: https://api.oasisdex.com/rest/v1
---

##### GET markets/

List all available markets

```bash
curl --request GET \
  --url {{ page.apiRoot }}/markets/
```

```javascript
200 OK
[
  {
    "pair": "MKR/ETH",     // Pair identifier
    "baseSymbol": "MKR",   // Base
    "quoteSymbol": "ETH",  // Quote
    "basePrecision": 18,   // Decimal base precision
    "quotePrecision": 18,  // Decimal quote precision
    "active":  true,       // Whether or not trading is enabled
    "time": "1511993944"   // Timestamp at which info was valid
  },
  {
    "pair": "ETH/DAI",
    "baseSymbol": "ETH",
    "quoteSymbol": "DAI",
    "basePrecision": 18,
    "quotePrecision": 18,
    "active":  true,
    "time": "1511993944"
  }
]
```

##### GET markets/abc/xyz/

High level overview of the state of a particular market.

```bash
curl --request GET \
  --url {{ page.apiRoot }}/markets/mkr/eth/
```

```javascript
200 OK
{
  "pair": "MKR/ETH",     // Pair identifier
  "last": "0.82652394",  // Most recent execution price
  "mid":  "0.82652394",  // (bid + ask) / 2
  "vol":  "3546.2452",   // 24h Volume
  "ask":  "0.87200000",  // Innermost ask
  "bid":  "0.82000000",  // Innermost bid
  "high": "0.88000000",  // 24h High
  "low":  "0.75600000",  // 24h Low
  "time": "1511993944"   // Timestamp at which info was valid
}
400 Bad Request
{
  "message": "Unknown pair"
}
```

##### GET markets/abc/xyz/price

Retrieve price info only

```bash
curl --request GET \
  --url {{ page.apiRoot }}/markets/mkr/eth/price
```

```javascript
200 OK
{
  "last": "0.82652394",  // Most recent execution price
  "mid":  "0.82652394",  // (bid + ask) / 2
  "time": "1511993944"   // Timestamp at which info was valid
}
400 BAD REQUEST
{
  "message": "Unknown pair"
}
```

##### GET markets/abc/xyz/volume

Retrieve volume info only

```bash
curl --request GET \
  --url {{ page.apiRoot }}/markets/mkr/eth/volume
```

```javascript
200 OK
{
  "vol":  "3546.2452",   // 24h Volume
  "time": "1511993944"   // Timestamp at which info was valid
}
400 BAD REQUEST
{
  "message": "Unknown pair"
}
```

##### GET markets/abc/xyz/book

Get the order book for a given pair

```bash
curl --request GET \
  --url {{ page.apiRoot }}/markets/mkr/eth/book
```

```javascript
200 OK
{
  "bids":[{
    "price":  "574.61",
    "amount": "0.1439327",
    "time":   "1511993944"
  }],
  "asks":[{
    "price":  "574.62",
    "amount": "19.1334",
    "time":   "1511993944"
  }]
}
400 BAD REQUEST
{
  "message": "Unknown pair"
}
```

##### GET markets/abc/xyz/trades

Get the list of trades for a given pair

```bash
curl --request GET \
  --url {{ page.apiRoot }}/markets/mkr/eth/book
```

```javascript
200 OK
[{
  "time":   "1511993944"
  "price":  "244.8",
  "amount": "0.03297384",
  "type":   "sell"
}]
400 BAD REQUEST
{
  "message": "Unknown pair"
}
```
