---
layout: oasis/api
title: Oasis API - Pairs
apiVersion: 2
---

##### GET pairs

Retrieve information on all available pairs.

```bash
curl -X GET {{ site.apiRootV2 }}/pairs
```

```javascript
200 OK
{
  "data":
  {
    "ETH/DAI":
    {
      "base": "ETH",          // Base token
      "quote": "DAI",         // Quote token
      "basePrecision": "18",  // Decimal base token precision
      "quotePrecision": "18", // Decimal quote token precision
      "active": true,         // Whether or not trading is enabled
    },
    ...
  },
  "time": "2019-07-10T16:20:40.639Z",  // Timestamp at which info was valid
  "message": "success"                 // Status message
}
```

##### GET pairs/`$base`/`$quote`

Retrieve information for a given pair of `$base` and `$quote`.

```bash
curl -X GET {{ site.apiRootV2 }}/pairs/eth/dai
```

```javascript
200 OK
{
  "data":
  {
    "base": "ETH",          // Base token
    "quote": "DAI",         // Quote token
    "basePrecision": "18",  // Decimal base token precision
    "quotePrecision": "18", // Decimal quote token precision
    "active": true,         // Whether or not trading is enabled
  },
  "time": "2019-07-10T16:20:40.639Z",  // Timestamp at which info was valid
  "message": "success"                 // Status message
}
400 Bad Request
{
  "time": "2019-07-10T16:20:40.639Z",
  "message": "Unknown pair"
}
```
