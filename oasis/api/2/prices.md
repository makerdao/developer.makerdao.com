---
layout: oasis/api
title: Oasis API - Prices
apiVersion: 2
---

##### GET prices

Retrieve price info for all known pairs.

```bash
curl -X GET {{ site.apiRootV2 }}/prices
```

```javascript
200 OK
{
  "data":
  {
    "ETH/DAI":
    {
      "24hrvwap":"1078.67340867",  // Volume weighted price over last 24 hours
      "12hrvwap":"951.51748486",   // Volume weighted price over last 12 hours
      "6hrvwap": "178.67340867",   // Volume weighted price over last 6 hours
      "1hrvwap": "91.51748486",    // Volume weighted price over last 1 hour
      "last":    "1063.16640000",  // Most recent trade execution price
    },
    ...
  },
  "time": "2019-06-13T10:49:40.639Z",  // Timestamp at which info was valid
  "message": "success"                 // Status message
}
```

##### GET prices/`$base`/`$quote`

Retrieve price info for a given pair of `$base` and `$quote`.

```bash
curl -X GET {{ site.apiRootV2 }}/prices/eth/dai
```

```javascript
200 OK
{
  "data":
  {
    "24hrvwap":"1078.67340867",  // Volume weighted price over last 24 hours
    "12hrvwap":"951.51748486",   // Volume weighted price over last 12 hours
    "6hrvwap": "178.67340867",   // Volume weighted price over last 6 hours
    "1hrvwap": "91.51748486",    // Volume weighted price over last 1 hour
    "last":    "1063.16640000",  // Most recent trade execution price
  }
  "time": "2019-06-13T10:49:40.639Z",  // Timestamp at which info was valid
  "message": "success"                 // Status message
}

400 BAD REQUEST
{
  "time": "2019-06-13T10:49:40.639Z",
  "message": "Unknown pair"
}
```
