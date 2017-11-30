---
layout: oasis/markets
title: Oasis Markets API
description: Public rest endpoints for markets data
---

##### GET markets/abc/xyz/book

Get the order book for a given pair

```bash
curl --request GET \
  --url {{ site.apiRoot }}/markets/mkr/eth/book
```

```javascript
200 OK
{
  "bids":[{
    "price":  "574.61",
    "amount": "0.1439327",
    "time":   "1511993944"
  }],
  "asks":[{
    "price":  "574.62",
    "amount": "19.1334",
    "time":   "1511993944"
  }]
}
400 BAD REQUEST
{
  "message": "Unknown pair"
}
```
