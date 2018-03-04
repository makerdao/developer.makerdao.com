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

![]({{ "images/graphql.png" | relative_url }})

##### Query IDE

A graphical interactive in-browser GraphQL IDE:

Current - [dai-ql.herokuapp.com/console](https://dai-ql.herokuapp.com/console)

Proposed - graphql.makerdao.com/v1/console

##### Query Endpoint

Current - [dai-ql.herokuapp.com/](https://dai-ql.herokuapp.com/)

Proposed - graphql.makerdao.com/v1/

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
