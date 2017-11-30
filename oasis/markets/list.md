---
layout: oasis/markets
title: Oasis Markets API - List
---

##### GET markets/

List all available markets

```bash
curl --request GET \
  --url {{ site.apiRoot }}/markets/
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
