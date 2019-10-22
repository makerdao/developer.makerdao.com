---
layout: oasis/api
title: Oasis API - Volumes
apiVersion: 2
---

##### GET volumes

Retrieve volume info for all known pairs.

```bash
curl -X GET {{ site.apiRootV2 }}/volumes
```

```javascript
200 OK
{
  "data":
  {
    "ETH/DAI":
    {
      "vol":  "3116.95771046",  // 24h Volume (base)
    },
    ...
  }
  "time": "2019-06-13T10:49:40.639Z",  // Timestamp at which info was valid
  "message": "success"                 // Status message
}
```

##### GET volumes/`$base`/`$quote`

Retrieve volume info for a given pair of `$base` and `$quote`.

```bash
curl -X GET {{ site.apiRootV2 }}/volumes/eth/dai
```

```javascript
200 OK
{
  "data":
  {
    "vol":  "3116.95771046",  // 24h Volume (base)
  },
  "time": "2019-06-13T10:49:40.639Z",  // Timestamp at which info was valid
  "message": "success"                 // Status message
}
400 BAD REQUEST
{
  "time": "2019-06-13T10:49:40.639Z",
  "message": "Unknown pair"
}
```
