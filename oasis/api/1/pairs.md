---
layout: oasis/api
title: Oasis Markets API - List
---

##### GET pairs/

Return information on all available pairs

```bash
curl --request GET \
  --url {{ site.apiRoot }}/pairs/
```

```javascript
200 OK
{
  "MKR/ETH":
  {
    "base": "MKR",          // Base
    "quote": "ETH",         // Quote
    "basePrecision": "18",  // Decimal base precision
    "quotePrecision": "18", // Decimal quote precision
    "active":  true,        // Whether or not trading is enabled
    "time": 1511993944      // Timestamp at which info was valid
  },
  "ETH/DAI":
  {
    "base": "ETH",
    "quote": "DAI",
    "basePrecision": "18",
    "quotePrecision": "18",
    "active":  true,
    "time": 1511993944
  },
  ...
}
```

##### GET pairs/abc/xyz

Return information for a specific pair

```bash
curl --request GET \
  --url {{ site.apiRoot }}/pairs/mkr/eth
```

```javascript
200 OK
{
  "base": "MKR",          // Base
  "quote": "ETH",         // Quote
  "basePrecision": "18",  // Decimal base precision
  "quotePrecision": "18", // Decimal quote precision
  "active":  true,        // Whether or not trading is enabled
  "time": 1511993944      // Timestamp at which info was valid
}
400 Bad Request
{
  "message": "Unknown pair"
}
```
