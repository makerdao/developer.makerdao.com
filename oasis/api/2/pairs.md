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
    "MKR/ETH":
    {
      "base": "MKR",          // Base
      "quote": "ETH",         // Quote
      "basePrecision": "18",  // Decimal base precision
      "quotePrecision": "18", // Decimal quote precision
      "active":  true,        // Whether or not trading is enabled
    },
    "ETH/DAI":
    {
      "base": "ETH",
      "quote": "DAI",
      "basePrecision": "18",
      "quotePrecision": "18",
      "active":  true,
    },
    ...
  },
  "time": "2019-06-13T10:49:40.639Z",  // Timestamp at which info was valid
  "message": "success"                 // Status message
}
```

##### GET pairs/`$base`/`$quote`

Retrieve information for a given pair of `$base` and `$quote`.

```bash
curl -X GET {{ site.apiRootV2 }}/pairs/mkr/eth
```

```javascript
200 OK
{
  "data":
  {
    "base": "MKR",          // Base
    "quote": "ETH",         // Quote
    "basePrecision": "18",  // Decimal base precision
    "quotePrecision": "18", // Decimal quote precision
    "active":  true,        // Whether or not trading is enabled
  },
  "time": "2019-06-13T10:49:40.639Z",  // Timestamp at which info was valid
  "message": "success"                 // Status message
}
400 Bad Request
{
  "time": "2019-06-13T10:49:40.639Z",
  "message": "Unknown pair"
}
```
