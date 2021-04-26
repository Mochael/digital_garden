---
title: What Database do I use
tree_state: 🌱
---

## Database Types
https://www.mongodb.com/nosql-explained

### SQL
Relational databases accessed by SQL (Structured Query Language). You can use SQL on these databases since they are relational databases where data is stored in tables that have fixed columns and rows.

- You can use an ORM (Object-Relational mappers) to simplify queries using the programming language of your choice with SQL databases

PostgreSQL and MySQL are the most popular
- Postgres is a feature-rich database that can handle complex queries and massive databases. Apparently it also has extensive support for NoSQL databases as well (can store JSON that doesn't need to fit relational constraints), making it very robust.
- MySQL is simpler database that’s relatively easy to set up and manage, fast, reliable, and well-understood.

### NoSQL
-   **Document databases** store data in documents similar to JSON (JavaScript Object Notation) objects. MongoDB is a document database. 
-   **Key-value databases** are a simpler type of database where each item contains keys and values. They essentially are a database for storing hash tables. Redis and DynanoDB are popular key-value databases.
-   **Wide-column stores** store data in tables, rows, and dynamic columns where each row is not required to have the same columns. Cassandra and HBase are two of the most popular wide-column stores.
-   **Graph databases** store data in nodes and edges. Nodes typically store information about people, places, and things while edges store information about the relationships between the nodes. Neo4j and JanusGraph are examples of graph databases.