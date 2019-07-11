---
layout: oasis/api
title: Oasis API - Trades
apiVersion: 2
---

##### GET trades/`$base`/`$quote`

Retrieve current and historical trades for a given pair of `$base` and `$quote`.

The `limit` parameter defines the trades count. The default value is 100.

The `fromId` parameter specifies the first trade identifier, by default the most recent trade.

```bash
# current trades
curl -X GET '{{ site.apiRootV2 }}/trades/eth/dai?limit=2'
```

```javascript
200 OK
{
  "data":
  [
    {
      "id": 12380,                        // Identifier
      "price": "298.45995966",            // Price
      "volume": "2.01022967",             // Volume (base)
      "time": "2019-07-01T08:22:53.000Z"  // Block time
    },
    {
      "id": 12379,                        // Identifier
      "price": "299.26565686",            // Price
      "volume": "1.33333333",             // Volume (base)
      "time": "2019-07-01T08:06:31.000Z"  // Block time
    }
  ]
  "time": "2019-07-08T15:29:40.639Z",  // Timestamp at which info was valid
  "message": "success"                 // Status message
}
400 Bad Request
{
  "time": "2019-07-08T15:29:40.639Z",
  "message": "Unknown pair"
}
```

```bash
# historical trades
curl -X GET '{{ site.apiRootV2 }}/trades/eth/dai?limit=2&fromId=12379'
```

```javascript
200 OK
{
  "data":
  [
    {
      "id": 12379,                        // Identifier
      "price": "299.26565686",            // Price
      "volume": "1.33333333",             // Volume (base)
      "time": "2019-07-01T08:06:31.000Z"  // Block time
    },
    {
      "id": 12378,                        // Identifier
      "price": "296.57000000",            // Price
      "volume": "49.15365893",            // Volume (base)
      "time": "2019-07-01T08:01:45.000Z"  // Block time
    }
  ]
  "time": "2019-07-08T15:29:40.639Z",  // Timestamp at which info was valid
  "message": "success"                 // Status message
}
400 Bad Request
{
  "time": "2019-07-08T15:29:40.639Z",
  "message": "Unknown pair"
}
```
