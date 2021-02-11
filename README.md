# OctoBay Subgraph

Endpoint: https://api.thegraph.com/subgraphs/name/octobay/octobay
Explorer: https://thegraph.com/explorer/subgraph/octobay/octobay

```
type User @entity {
  id: ID!
  name: String!
  ethAddress: Bytes!
  status: Int!
}

type Issue @entity {
  id: ID!
  deposits: [IssueDeposit!]! @derivedFrom(field: "issue")
}

type IssueDeposit @entity {
  id: ID!
  from: Bytes!
  amount: BigInt!
  issue: Issue!
}

type Oracle @entity {
  id: ID!
  name: String!
  ethAccount: Bytes!
  jobs: [OracleJob!]! @derivedFrom(field: "oracle")
}

type OracleJob @entity {
  id: ID!
  name: String!
  fee: BigInt!
  oracle: Oracle!
}

```
