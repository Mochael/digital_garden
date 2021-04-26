---
title: What is a Object Relational Mapper
tree_state: 🌱
---

## What is an ORM
Object-relational-mappers allow you to write queries to an SQL ([[What Database do I use]]) database using the object-oriented paradigm of your preferred programming language. SQL code can get pretty complicated once you start writing advancedd queries, so using an ORM makes it easier to write complicated queries on your database.

Using an ORM abstracts away the database system so that you can easily switch from say MySQL to PostgreSQL.



## Popular ORMs
- [TypeORM](https://typeorm.io/#/) 
	- runs in a variety of environments including node.js, React Native, Electron
	- can be used with TypeScript or JavaScript
	- supports MySQL / MariaDB / Postgres / CockroachDB / SQLite / Microsoft SQL Server / Oracle / SAP Hana / sql.js
	-  also supports MongoDB NoSQL database
- [Prisma.js](https://www.prisma.io/)
	- Runs with Node.js
	- must be used with Typescript
	- supports PostgreSQL, MySQL, and SQLite databases


## NoSQL ORMs
NoSQL Databases have similar tools like ORMs to map objects to the database, but they are specific depending on the type of database. MongoDB for example which is a document based database, has the package [mongoose](https://mongoosejs.com/) which is called an ODM on the other hand is an Object Document Mapper (ODM).