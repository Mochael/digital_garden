---
title: How to Build a Full Stack Application
tree_state: 🌱
---

# Frontend
User interface that displays information and makes calls to the API to update it.

### Tools to Build It
Languages:
- Javascript/Typescript, HTML, CSS

Frameworks:
- React
	- Next.js ([[What is Next.js]])
- Svelte ([[What is Svelte]])
- Vue.js ([[What is Vue.js]])

# Backend

### Tools to Build It
All in one:
- Firebase (you can use this and they take care of the entirety of the API and the database)

## API
Queries database, edits database, manipulates data, and sends information to the front end. Your logic for interacting with the database should not be exposed in front end, instead the frontend has access to API end-points to call your API to fetch information from the database.

### Tools to Build It
API Server:
- Express.js ([[What is Express.js]])
	- Apollo (implementation of GraphQL and with a server you can run)

Simplify Data Fetching API Calls:
- GraphQL ([[What is GraphQL]])

## Database
Stores data from the app to be stored and later fetched for users.

### Tools to Build It
Main Database:
- PostgresSQL ([[What Database do I use]])

Caching Data:
- Redis ([[What is Redis]])

Making database queries easier:
- TypeORM ([[What is a Object Relational Mapper]])

Searching Data
- Elasticsearch ([[What is Elasticsearch]])