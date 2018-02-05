---
layout: oasis/api
title: Oasis API - Volumes
---

##### GET volumes/

Retrieve volume info for all pairs

```bash
curl --request GET \
  --url {{ site.apiRoot }}/volumes/
```

```javascript
200 OK
{
  "data":
  {
    "MKR/ETH":                   //Token Pair
    {
      "vol":  "3546.24524654"    // 24h Volume
    },
    ...
  },
  "time": 1511993944,            // Unix timestamp at which info was valid
  "message": "success"           // Satus message
}
```

##### GET volumes/abc/xyz

Retrieve volume info for a given pair

```bash
curl --request GET \
  --url {{ site.apiRoot }}/volumes/mkr/eth
```

```javascript
200 OK
{
  "data":
  {
    "vol":  "3546.24524654"      // 24h Volume
  },
  "time": 1511993944,            // Unix timestamp at which info was valid
  "message": "success"           // Status message
}
400 BAD REQUEST
{
  "data": {},
  "time":  1511993944,
  "message": "Unknown pair"
}
```
