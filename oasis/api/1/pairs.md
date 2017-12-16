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
  "time": 1513379816,         // Unix timestamp at which info was valid
  "message": "success"        // Status message
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
  "data":
  {
    "base": "MKR",          // Base
    "quote": "ETH",         // Quote
    "basePrecision": "18",  // Decimal base precision
    "quotePrecision": "18", // Decimal quote precision
    "active":  true,        // Whether or not trading is enabled
  },
  "time": 1513379816,       // Unix timestamp at which info was valid
  "message": "success"      // Status message
}
400 Bad Request
{
  "data": {},
  "time": 1513379816,
  "message": "Unknown pair"
}
```
