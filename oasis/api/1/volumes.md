---
layout: oasis/api
title: Oasis Markets API
description: Public rest endpoints for markets data
---

##### GET volumes/

Retrieve volume info for all pairs

```bash
curl --request GET \
  --url {{ site.apiRoot }}/volumes/
```

```javascript
200 OK
[
  {
    "vol":  "3546.2452",   // 24h Volume
    "time": "1511993944"   // Timestamp at which info was valid
  },
  ...
]
```

##### GET volumes/abc/xyz

Retrieve volume info for a given pair

```bash
curl --request GET \
  --url {{ site.apiRoot }}/volumes/mkr/eth/
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
