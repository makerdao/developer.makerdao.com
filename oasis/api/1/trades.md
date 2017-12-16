---
layout: oasis/api
title: Oasis Markets API
description: Public rest endpoints for markets data
---

##### GET trades/abc/xyz

Get the list of trades for a given pair

```bash
curl --request GET \
  --url {{ site.apiRoot }}/trades/mkr/eth/
```

```javascript
200 OK
{
  "data":
  {
    [
      {
        "price": "0.92000000",            // Price trade was executed at
        "buyToken": "MKR",		            // Token bought
        "payToken": "ETH",		            // Token paid
        "buyAmount": "0.75515217",	      // Amount of token bought
        "payAmount": "0.69474000",	      // Amount of token paid
        "type": "SELL",		                // Type of trade
        "time": "1513115304"		          // Unix timestamp when trade was executed
      },
      ...
    ]
  },
  "time": 1513382496,                     // Unix timestamp at which info was valid
  "message": "success"                    // Status message

200 OK
{
  "data": {},
  "time": 1513382496,                     // Unix timestamp at which info was valid
  "message": "No recent trade history"    // Status message
}

400 BAD REQUEST
{
  "data": {},
  "time": 1513382496,
  "message": "Unknown pair"
}
```
