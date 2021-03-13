---
title: Database vs Data Warehouse vs Data Lake
tree_state: 🌱
---

## Database
- Stores relational tables typically with defined schema (i.e.say we have a table storing employee info, the fields for employee info won't typically change because we always define employees the same way)
- Optimized to deal with transactions, for example editing a table to add a new user. 
	- Is not optimized to perform data analytics

## Data Warehouse
- Exists on top of several databases that consumes data from the databases and creates an interface for you to query the data in the databases
- Is optimized for data analytics

## Data Lake
- A centralized repository that is used to store any kind of structured or unstructured data that doesn't impose any structure (schemas) on the data
- Basically you throw whatever you want into the data lake and just leave it there for safe keeping. Because you don't have any schemas you can't really extract, transform, load (ETL) the data for analysis. What you do is export the data in its raw form, and then you can define it's structure afterwards.