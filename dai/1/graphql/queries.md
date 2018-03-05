---
layout: dai/graphql
title: Dai
subtitle: GraphQL - Queries
---

#### getCup
_Query a specific Cup by Id_

Example: Retrieve Cup 3 `lad`, `ink` and `art` attributes along with 5 most
recent actions. The top level attributes in this query represent the current
cup state whilst the attributes in the history represent the state at a
particular block height.

```graphql
{
  getCup(id: 3) {
    lad
    art
    ink
    history(first: 5) {
      nodes {
        act
        arg
        block
        time
        ink
        art
      }
    }
  }
}
```

#### allCups
_Query across all Cups_

Example: Retrieve the first 10 active cups with the lowest collateralisation
ratio along with 5 most recent actions, the total number of cups matching the
query, and pagination info.

```graphql
{
  allCups(
    first: 10,
    condition: { deleted: false },
    orderBy: RATIO_ASC
  ) {
    totalCount
    pageInfo {
      hasNextPage
      hasPreviousPage
      endCursor
    }
    nodes {
      id
      lad
      art
      ink
      ratio
      history(first: 5) {
        nodes {
          act
          time
        }
      }
    }
  }
}
```

#### allCupActs
_Query history across all Cup Actions_

Example: Retrieve the 10 most recent `bite` acts.

```graphql
{
  allCupActs(
    first: 10,
    orderBy: BLOCK_DESC,
    condition: { act: BITE }
  ) {
    nodes {
      id
      lad
      art
      ink
    }
  }
}
```
