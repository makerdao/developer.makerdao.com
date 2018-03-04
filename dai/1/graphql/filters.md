---
layout: dai/graphql
title: Dai
subtitle: GraphQL - Filters
---

#### Condition

Use `condition:` to filter a result set by matching argument:


```graphql
query {
  allCupActs(condition: { act: BITE }) {
    ...
  }
}
```

#### Filter

For more complex comparisons use the `filter:` argument:

Comparison operator with array input:

```graphql
query {
  allCups(filter: { id: { in: [1, 2] } }) {
    ...
  }
}
```

Comparison operator with scalar input:

```graphql
query {
  allCups(filter: { time: { greaterThan: "2018-01-01" } }) {
    ...
  }
}
```

Multiple comparison operators:

```graphql
query {
  allCups(filter: { time: { greaterThan: "2018-01-01" } }) {
    ...
  }
}
```

#### Operators

- null
- equalTo
- notEqualTo
- lessThan
- lessThanOrEqualTo
- greaterThan
- greaterThanOrEqualTo
- in
- notIn
