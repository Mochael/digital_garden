---
title: What is Redis
tree_state: 🌱
---

Redis stands for **Re**mote **Di**ctionary **S**erver and is a key-value database ([[What Database do I use]]). All Redis data resides in-memory, in contrast to databases that store data on disk or SSDs, which let's Redis access data in microseconds. Redis supports time-to-live (TTL) which lets you limit the lifetime of certain data.

Redis can be useful for storing both information into the cache as well as session storage ([[Cache vs Session Store]]). However since it is in memory storage it can take up a lot of space if you have a bunch of users all with their sessions stored (check out https://liferay.dev/blogs/-/blogs/session-storage-is-evil).

[Memcached](https://memcached.org/) is an alternative to Redis; see https://aws.amazon.com/elasticache/redis-vs-memcached/ for a comparison.