---
layout: oasis/api
title: Oasis Markets API
description: Public rest endpoints for markets data
---

##### GET prices/

Retrieve price info for all pairs

```bash
curl --request GET \
  --url {{ site.apiRoot }}/prices/
```

```javascript
200 OK
[
  {
    "last": "0.82652394",  // Most recent execution price
    "mid":  "0.82652394",  // (bid + ask) / 2
    "time": "1511993944"   // Timestamp at which info was valid
  },
  ...
]
```

##### GET prices/abc/xyz/

Retrieve price info for a given pair

```bash
curl --request GET \
  --url {{ site.apiRoot }}/prices/mkr/eth/
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
