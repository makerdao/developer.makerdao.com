---
layout: oasis/api
title: Oasis API - Markets
---

##### GET markets/

High level overview of all active markets.

```bash
curl --request GET \
  --url {{ site.apiRoot }}/markets/
```

```javascript
200 OK
{
  "data":
  {
    "MKR/ETH":
    {
      "pair": "MKR/ETH",     // Pair identifier
      "price":"0.84157326",  // 6h Volume weighted price
      "last": "0.82652394",  // Most recent execution price
      "vol":  "3546.2452",   // 24h Volume
      "ask":  "0.87200000",  // Innermost ask
      "bid":  "0.82000000",  // Innermost bid
      "low":  "0.75600000",  // 24h Low
      "high": "0.88000000",  // 24h High
      "active":true          // Whether or not trading is enabled
    },
    ...
  }
  "time": 1513280933,        // Unix timestamp at which info was valid
  "message": "success"       // Status message
}
```

##### GET markets/abc/xyz

High level overview of the state of a particular market.

```bash
curl --request GET \
  --url {{ site.apiRoot }}/markets/mkr/eth
```

```javascript
200 OK
{
  "data":
  {
    "pair": "MKR/ETH",     // Pair identifier
    "price":"0.84157326",  // 6h Volume weighted price
    "last": "0.82652394",  // Most recent execution price
    "vol":  "3546.2452",   // 24h Volume
    "ask":  "0.87200000",  // Innermost ask
    "bid":  "0.82000000",  // Innermost bid
    "low":  "0.75600000",  // 24h Low
    "high": "0.88000000",  // 24h Highs
    "active":true          // Whether or not trading is enabled
  },
  "time": 1513280933,      // Unix timestamp at which info was valid
  "message": "success"     // Status message
}
400 Bad Request
{
  "data": {},
  "time": 1513280933,
  "message": "Unknown pair"
}
```

