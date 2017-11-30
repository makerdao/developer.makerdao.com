---
layout: oasis/markets
title: Oasis Markets API
description: Public rest endpoints for markets data
---

##### GET markets/abc/xyz/price

Retrieve price info only

```bash
curl --request GET \
  --url {{ site.apiRoot }}/markets/mkr/eth/price
```

```javascript
200 OK
{
  "last": "0.82652394",  // Most recent execution price
  "mid":  "0.82652394",  // (bid + ask) / 2
  "time": "1511993944"   // Timestamp at which info was valid
}
400 BAD REQUEST
{
  "message": "Unknown pair"
}
```
