---
layout: oasis/markets
title: Oasis Markets API
description: Public rest endpoints for markets data
---

##### GET markets/abc/xyz/

High level overview of the state of a particular market.

```bash
curl --request GET \
  --url {{ site.apiRoot }}/markets/mkr/eth/
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

