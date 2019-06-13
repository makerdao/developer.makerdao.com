---
layout: oasis/api
title: Oasis API - Markets
apiVersion: 2
---

##### GET markets/

Show high level overview of all known markets.

```bash
curl --request GET \
  --url {{ site.apiRootV2 }}/markets/
```

```javascript
200 OK
{
  "data":
  {
    "ETH/DAI":
    {
      "pair": "ETH/DAI",        // Pair identifier
      "price":"1078.67340867",  // 24h Volume weighted price
      "last": "1063.16640000",  // Most recent execution price
      "vol":  "3116.95771046",  // 24h Volume (base)
      "ask":  "1063.87200000",  // Innermost ask
      "bid":  "1063.82000000",  // Innermost bid
      "low":  "917.59999999",   // 24h Low
      "high": "1229.80000000",  // 24h High
    },
    ...
  }
  "time": "2019-06-13T10:49:40.639Z",  // Timestamp at which info was valid
  "message": "success"                 // Status message
}
```

##### GET markets/`$base`/`$quote`

Show high level overview of markets for trading `$base` with `$quote`.

```bash
curl --request GET \
  --url {{ site.apiRootV2 }}/markets/mkr/eth
```

```javascript
200 OK
{
  "data":
  {
    "pair": "ETH/DAI",        // Pair identifier
    "price":"1078.67340867",  // 24h Volume weighted price
    "last": "1063.16640000",  // Most recent execution price
    "vol":  "3116.95771046",  // 24h Volume (base)
    "ask":  "1063.87200000",  // Innermost ask
    "bid":  "1063.82000000",  // Innermost bid
    "low":  "917.59999999",   // 24h Low
    "high": "1229.80000000",  // 24h High
  },
  "time": "2019-06-13T10:49:40.639Z",  // Timestamp at which info was valid
  "message": "success"                 // Status message
}
400 Bad Request
{
  "data": {},
  "time": "2019-06-13T10:49:40.639Z",
  "message": "Unknown pair"
}
```
