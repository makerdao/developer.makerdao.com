---
layout: dai/graphql
title: Dai
subtitle: GraphQL
---

#### GraphQL

GraphQL is a query language for APIs and a runtime for fulfilling those
queries. It provides a complete and understandable description of the
available data, and gives clients the power to ask for exactly what they need
and nothing more.

API Status: Unstable

Query IDE available at:

- Current: [dai-ql.herokuapp.com/v1/console](https://dai-ql.herokuapp.com/console)

- Proposed: [graphql.makerdao.com/v1/console](https://dai-ql.herokuapp.com/console)


Dai 1.0 Query Endpoint:

- Current: [dai-ql.herokuapp.com/](https://dai-ql.herokuapp.com/)

- Proposed: [graphql.makerdao.com/v1/](https://dai-ql.herokuapp.com/)

Example:

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

Libraries:

[graphql.org/code/](http://graphql.org/code/)

[Appolo Client](https://www.apollographql.com/client)

[Relay](https://facebook.github.io/relay/docs/en/introduction-to-relay.html)
