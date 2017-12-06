---
layout: oasis/api
title: Oasis Markets API
description: Public rest endpoints for markets data
---

##### GET trades/abc/xyz

(not implemented)

Get the list of trades for a given pair

```bash
curl --request GET \
  --url {{ site.apiRoot }}/trades/mkr/eth/
```

```javascript
200 OK
[{
  "time":   "1511993944"
  "price":  "244.8",
  "amount": "0.03297384",
  "type":   "sell"
}]
400 BAD REQUEST
{
  "message": "Unknown pair"
}
```
