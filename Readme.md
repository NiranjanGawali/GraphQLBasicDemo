# Apollo Server GraphQL Operations

This document outlines how to perform GraphQL operations such as querying, adding, editing, and deleting records in an Apollo Server setup. Below are examples of different operations with their respective queries, mutations, and variables.

## 1. Query Multiple Records

To retrieve a list of games, use the following GraphQL query:

```graphql
query GameQuery {
  games {
    id
    title
    platform
  }
}
```

## 2. Query a Single Record

To fetch details of a single game by its id, use the following query:

```graphql
query GameQuery($id: ID!) {
  game(id: $id) {
    id
    title
    platform
  }
}
```

### Variables:

```graphql
{
  "id": "2"
}
```

## 3. Delete Mutation

To delete a game record by its id, use the mutation below:

```graphql
mutation DeleteMutation($id: ID!) {
  deleteGame(id: $id) {
    id
    title
    platform
  }
}
```

### Variables:

```graphql
{
  "id": "1"
}
```

## 4. Add Mutation

To add a new game record, use this mutation:

```graphql
mutation AddMutation($game: AddGameInput!) {
  addGame(game: $game) {
    id
    title
    platform
  }
}
```

### Variables:

```graphql
{
  "game": {
    "title": "a new game title",
    "platform": ["Rings of power"]
  }
}
```

## 5. Edit Mutation

To update an existing game record by its id, use this mutation:

```graphql
mutation EditMutation($id: ID!, $editGame: EditGameInput!) {
  updateGame(id: $id, editGame: $editGame) {
    title
    platform
  }
}
```

### Variables:

```graphql
{
  "editGame": {
    "title": "a new gameddd",
    "platform": ["Rings of power"]
  },
  "id": "2"
}
```
