---
layout: oasis/markets
title: Oasis Markets API
description: Public rest endpoints for markets data
---

##### GET markets/abc/xyz/volume

Retrieve volume info only

```bash
curl --request GET \
  --url {{ site.apiRoot }}/markets/mkr/eth/volume
```

```javascript
200 OK
{
  "vol":  "3546.2452",   // 24h Volume
  "time": "1511993944"   // Timestamp at which info was valid
}
400 BAD REQUEST
{
  "message": "Unknown pair"
}
```
