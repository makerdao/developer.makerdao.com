---
layout: oasis/api
title: Oasis Markets API
description: Public rest endpoints for markets data
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
  "MKR/ETH":
  {
    "pair": "MKR/ETH",     // Pair identifier
    "price":"0.84157326",  // 24h Volume weighted price 
    "last": "0.82652394",  // Most recent execution price
    "vol":  "3546.2452",   // 24h Volume
    "ask":  "0.87200000",  // Innermost ask
    "bid":  "0.82000000",  // Innermost bid
    "low":  "0.75600000",  // 24h Low
    "high": "0.88000000",  // 24h High
    "active":true          // Whether or not trading is enabled
    "time": 1511993944     // Timestamp at which info was valid
  },
  ...
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
  "pair": "MKR/ETH",     // Pair identifier
  "price":"0.84157326",  // 24h Volume weighted price
  "last": "0.82652394",  // Most recent execution price
  "vol":  "3546.2452",   // 24h Volume
  "ask":  "0.87200000",  // Innermost ask
  "bid":  "0.82000000",  // Innermost bid
  "low":  "0.75600000",  // 24h Low
  "high": "0.88000000",  // 24h Highs
  "active":true          // Whether or not trading is enabled
  "time": 1511993944     // Timestamp at which info was valid
}
400 Bad Request
{
  "message": "Unknown pair"
}
```

