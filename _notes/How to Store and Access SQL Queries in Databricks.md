---
title: How to Store and Access SQL Queries in Databricks
tree_state: 🌱
---

1. Create the SQL query and define `table_name` as the name where you store the queried table.
```
%sql
CREATE OR REPLACE TEMPORARY VIEW <table_name> AS 

'''SQL query here'''
SELECT * FROM <data_table>
```

2. Create a spark dataframe for the queried table
```
spark_dataframe_of_table = spark.table('table_name')
```