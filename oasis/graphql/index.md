---
layout: oasis/graphql
title: Oasis Query API
subtitle: GraphQL
---

### Oasis Query API beta

GraphQL is a query language for APIs and a runtime for fulfilling those
queries. It provides a complete and understandable description of the
available data, and gives clients the power to ask for exactly what they need
and nothing more.

Try out the api in the interactive [console](https://data.makerdao.com/v1/console).

Tip: use the `_`underscore to trigger a list of available fields for autocompleting queries.

---

![]({{ "images/graphql.oasis.png" | relative_url }})

---

##### Usage

If you're new to GraphQL you might want to start [here](https://graphql.org).

Interact programatically at: [data.makerdao.com/v1](https://data.makerdao.com/v1)

```bash
$ curl -XPOST  \
       -H "Content-Type:application/graphql" \
       -d 'query { allOasisTrades { totalCount } }' \
       https://data.makerdao.com/v1

  {
    "data": {
      "allOasisTrades": {
        "totalCount":23756
      }
    }
  }
```

##### Client Libraries

For simple requests over http you might want to check out [GraphQL
Request](https://github.com/prismagraphql/graphql-request).

There's also the React-friendly
[Relay](https://facebook.github.io/relay/docs/en/introduction-to-relay.html)
library.

And many more [here](http://graphql.org/code/#graphql-clients).
