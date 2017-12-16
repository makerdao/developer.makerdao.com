---
layout: oasis/api
title: Oasis Markets API
description: Public rest endpoints for markets data
---

##### GET orders/abc/xyz

(not implemented)

Get the order book for a given pair

```bash
curl --request GET \
  --url {{ site.apiRoot }}/orders/mkr/eth/
```

```javascript
200 OK
{
  "data":
  { 
    "bids":
    [
      {
        "price":  "574.61",       // Offer price for base token denominated in quote token
        "amount": "0.1439327",    // Amount of base token
        "time":   "1511993944"    // Unix timestamp at which info was valid
      },
      ...
    ],
    "asks":
    [
      {
        "price":  "574.62",       // Offer price for base token denominated in quote token
        "amount": "19.1334",      // Amount of base token
        "time":   "1511993944"    // Unix timestamp at which info was valid
      },
      ...
    ]
  },
  "time": "1511993944",           // Unix timestamp at which info was valid
  "message": "success"            // Status message
}
400 BAD REQUEST
{
  "data": {},
  "time": "1511993944",
  "message": "Unknown pair"
}
```
