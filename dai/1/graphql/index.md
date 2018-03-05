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

Explore the API via the interactive [in-browser IDE](https://graphql.makerdao.com/v1/console):

![]({{ "images/graphql.png" | relative_url }})

##### Query Endpoint

Interact with the API programatically via: [graphql.makerdao.com/v1](https://graphql.makerdao.com/v1)

```bash
$ curl -XPOST  \
       -H "Content-Type:application/graphql" \
       -d 'query { getCup(id: 100) { id lad } }' \
       http://graphql.makerdao.com/v1

  {
    "data": {
      "cup": {
        "id":100,
        "lad":"0xcE60Fa6BCb3Ba6FDE3d6b8196513458c00986E73"
      }
    }
  }
```

##### Client Libraries

Golang

- [graphql](https://github.com/shurcooL/graphql#readme)

Javascript

- [Apollo](https://www.apollographql.com/client)

- [Relay](https://facebook.github.io/relay/docs/en/introduction-to-relay.html)

- [GraphQL Request](https://github.com/graphcool/graphql-request)

- [Lokka](https://github.com/kadirahq/lokka)

- [Nano](https://github.com/yoshuawuyts/nanogql)

iOS

- [Apollo iOS](https://www.apollographql.com/docs/ios/)

- [GraphQL iOS](https://github.com/funcompany/graphql-ios)

Python

- [GQL](https://github.com/graphql-python/gql)

Others

- [graphql.org/code](http://graphql.org/code/#graphql-clients)
