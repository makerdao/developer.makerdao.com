---
layout: dai/graphql
title: Dai
subtitle: GraphQL -Types
---

#### Types

GraphQL Schema Definition

```graphql
type Cup {
  # owner
  lad: String!

  # collateral
  ink: String!

  # debt
  art: String!
  tab: String!

  # fee
  ire: String!
  rap: String!

  # timestamps
  created: Block!
  createdTimestamp: DateTime!
  updated: Block!
  updatedTimestamp: DateTime!

  state: CupState!

  events: [Event!]

  # ???
  # Collateralization Ratio

  # ???
  # Liquidation Price
}

type Price {
  base: Symbol!,
  quote: Symbol!,
  price: Float!,
  block: Block!
}

type CupAction {
  action: Action!,
  created: Block!
  createdTimestamp: DateTime!,
  sender: Address!,
  cupID: Int,
  data: String,
  txHash: String
}

type Query {

  # Find a cup by ID
  #
  # Arguments
  # id: The cup ID.
  # block: Optionally specify a block height
  getCup(
    id: Int!,
    block: Block
  ): Cup

  # Perform a search across cups
  #
  # Arguments
  # first: Returns the first _n_ elements from the list.
  # last: Returns the last _n_ elements from the list.
  # before: Returns the elements in the list that come before the
  # specified cup ID.
  # after: Returns the elements in the list that come after the
  # specified cup ID.
  # beforeBlock: Returns the elements in the list that come before the
  # specified block height.
  # after: Returns the elements in the list that come after the
  # specified block height.
  # lad: Returns cups belonging to the specified address
  # block: Block height
  # states: Return cups with states in the specified list
  allCups(
    first: Int,
    last: Int,
    before: Int,
    after: Int,
    beforeBlock: Block,
    afterBlock: Block,
    lad: Address
    states: [String]
  ): [Cup]

  # Perform a search across cup actions
  #
  # Arguments
  # first: Returns the first _n_ elements from the list.
  # last: Returns the last _n_ elements from the list.
  # after: Returns the elements in the list that come after the
  # specified block.
  # before: Returns the elements in the list that come before the
  # specified block.
  # sender: Returns events by sender
  # actions: Return events with actions in the specified list
  allCupActs(
    first: Block,
    after: Block,
    last: Block,
    before: Block,
    sender: Address,
    actions: [Action]
  )

  air: String
  axe: String
  chi: String
  fee: String
  fit: String
  fix: String
  fog: String
  cap: String
  ice: String
  ink: String
  joy: String
  mat: String
  par: String
  per: String
  pie: String
  pep: String
  pip: String
  rhi: String
  s2s: String
  tag: String
  tapAsk: String
  tapBid: String
  tapGap: String
  tau: String
  tax: String
  tubAsk: String
  tubBid: String
  tubGap: String
  way: String
  woe: String
}

enum CupState {
  EMPTY
  FUNDED
  DRAWN
}

enum Acts {
  JOIN
  EXIT
  BOOM
  BUST
  CAGE
  CASH
  OPEN
  GIVE
  LOCK
  FREE
  DRAW
  WIPE
  SHUT
  BITE
}

scalar Address
scalar Block
```
