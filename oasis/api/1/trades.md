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
[{
  "price": "0.92000000",            //price trade was executed at
  "buyToken": "MKR",		    //token bought
  "payToken": "ETH",		    //token paid
  "buyAmount": "0.75515217",	    //amount of token bought
  "payAmount": "0.69474000",	    //amount of token paid
  "type": "SELL",		    //type of trade
  "time": "1513115304"		    //unix timestamp when trade was executed
}]

200 OK
{
  "message": "No recent trade history"
}

400 BAD REQUEST
{
  "message": "Unknown pair"
}
```
