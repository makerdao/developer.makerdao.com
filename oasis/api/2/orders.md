---
layout: oasis/api
title: Oasis API - Orders
apiVersion: 2
---

##### GET offers

Retrieve current orderbook for all known markets.

Returns at most 100 orders for each side.

```bash
curl -X GET {{ site.apiRootV2 }}/offers
```

```javascript
200 OK
{
  "data":
  {
    "ETH/DAI":
    {
      "bids": [
        ["292.90600000", "12.20186681"],  // Best offer: price, volume (base)
        ["292.79972194", "10.00000000"],  // 2nd offer: price, volume (base)
        ...
      ],
      "asks": [
        ["296.16000000", "12.10000000"],  // Best offer: price, volume (base)
        ["296.25000000", "43.50676794"],  // 2nd offer: price, volume (base)
        ...
      ]
    },
    ...
  }
  "time": "2019-07-08T15:29:40.639Z",  // Timestamp at which info was valid
  "message": "success"                 // Status message
}
```

##### GET offers/`$base`/`$quote`

Retrieve current orderbook for a given pair of `$base` and `$quote`.

```bash
curl -X GET {{ site.apiRootV2 }}/offers/eth/dai
```

```javascript
200 OK
{
  "data":
  {
    "bids": [
      ["292.90600000", "12.20186681"],  // Best offer: price, volume (base)
      ["292.79972194", "10.00000000"],  // 2nd offer: price, volume (base)
      ...
    ],
    "asks": [
      ["296.16000000", "12.10000000"],  // Best offer: price, volume (base)
      ["296.25000000", "43.50676794"],  // 2nd offer: price, volume (base)
      ...
    ]
  },
  "time": "2019-07-08T15:29:40.639Z",  // Timestamp at which info was valid
  "message": "success"                 // Status message
}
400 Bad Request
{
  "time": "2019-07-08T15:29:40.639Z",
  "message": "Unknown pair"
}
```
