---
layout: oasis/api
title: Oasis API - Prices
apiVersion: 1
---

##### GET prices/

Retrieve price info for all pairs

```bash
curl --request GET \
  --url {{ site.apiRoot }}/prices/
```

```javascript
200 OK
{
  "data":
  {
    "MKR/ETH":
    {
          "24hrvwap":"0.87493281",  // Volume weighted price over last 24 hours
          "12hrvwap":"0.87960677",  // Volume weighted price over last 12 hours
          "6hrvwap":"0.88000000",   // Volume weighted price over last 6 hours
          "1hrvwap":"0.88000000",   // Volume weighted price over last 1 hour
          "last": "0.82652394",     // Most recent trade execution price
    },
    ...
  },
  "time": 1513381455,               // Unix timestamp at which info was valid
  "message": "success"              // Status message
}
```

##### GET prices/abc/xyz

Retrieve price info for a given pair

```bash
curl --request GET \
  --url {{ site.apiRoot }}/prices/mkr/eth
```

```javascript
200 OK
{
  "data":
  {
    "24hrvwap":"0.87493281",  // Volume weighted price over last 24 hours
    "12hrvwap":"0.87960677",  // Volume weighted price over last 12 hours
    "6hrvwap":"0.88000000",   // Volume weighted price over last 6 hours
    "1hrvwap":"0.88000000",   // Volume weighted price over last 1 hour
    "last": "0.82652394",     // Most recent trade execution price
  }
  "time": 1513381455,         // Unix timestamp at which info was valid
  "message": "success"        // Status message
}

400 BAD REQUEST
{
  "data": {},
  "time": 1513381455,
  "message": "Unknown pair"
}
```
