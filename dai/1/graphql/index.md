---
layout: dai/graphql
title: Dai
subtitle: GraphQL
---

### GraphQL

GraphQL is a query language for APIs and a runtime for fulfilling those
queries. It provides a complete and understandable description of the
available data, and gives clients the power to ask for exactly what they need
and nothing more.

##### Console

Explore the API via the interactive [in-browser IDE](https://dai-ql.herokuapp.com/console):

![]({{ "images/graphql.png" | relative_url }})

##### Query Endpoint

Interact with the API programatically via: [graphql.makerdao.com](https://dai-ql.herokuapp.com/)

```bash
$ curl -XPOST  \
       -H "Content-Type:application/graphql" \
       -d 'query { getCup(id: 100) { id lad } }' \
       http://dai-ql.herokuapp.com/

  {
    "data": {
      "cup": {
        "id":100,
        "lad":"0xcE60Fa6BCb3Ba6FDE3d6b8196513458c00986E73"
      }
    }
  }
```

##### Libraries

[graphql.org/code/](http://graphql.org/code/)

[Apollo Client](https://www.apollographql.com/client)

[Relay](https://facebook.github.io/relay/docs/en/introduction-to-relay.html)
