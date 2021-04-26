---
title: What is GraphQL
tree_state: 🌱
---

## REST APIs
Traditional REST APIs fetch information about specific resources (a resource could be a user, a blog post, etc.) by sending a GET request to that resource's URL (called an endpoint). For example, fetching info about a specific user would go to `/users/<id>` and fetch information about all that user's blog posts we would send a GET request to `/users/<id>/posts`. To make complex queries with a REST API you would often need to either: send multiple requests, create a new resource containing the information you want in the backend, or include some special parameters in the URL that tell you you need to perform some complex logic in the response.

## GraphQL
GraphQL is a language and runtime for executing queries  to create APIs as an alternative to REST APIs. GraphQL uses only a single endpoint for fetching data and allows you to define precisely what fields in your data you want to fetch for each query. This makes querying much simpler and eliminates the problem of over/under-fetching data that was typical with REST APIs, since you can always query directly what you want.

### Different Parts of GraphQL
1. In frontend you use GraphQL language send a query for specific data to be fetched from backend.
2. In backend you have already defined a **schema** to describe the shape of your data graph. This schema defines a hierarchy of **types** with fields that are populated from your back-end data stores. The schema also specifies exactly what read (**queries**) and write (**mutations**) operations are available for clients to execute against your data graph.
3. GraphQL server executes query and passes data back to the client.

## Servers that Run GraphQL
**Apollo** is the most popular implementation of GraphQL that also provides a bunch of extra libraries and the ability to run the API on their servers.

You can also create your own server to run the API using Express  ([[What is Express.js]]) as shown https://graphql.org/graphql-js/running-an-express-graphql-server/.


## Type-safe GraphQL API

[TypeGraphQL](https://typegraphql.com/) is a framework for building GraphQL APIs with Node.js and TypeScript. It is designed to work well with ORMs and simplify complicated Typscript code that's needed with normal GraphQL to write query resolvers (A resolver is a function that's responsible for populating the data for a single field in your schema) and define your schema (see https://typegraphql.com/blog/2018/03/25/medium-article.html).

Combining TypeGraphQL and TypeORM ([[What is a Object Relational Mapper]]) allows us to create a type-safe GraphQL API.