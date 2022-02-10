---
title: What is object serialization
tree_state: 🌱
---

Object serialization is when you convert an object that is currently stored in whatever runtime you are using into bytes such that it can be stored entirely in a database and be deserialized (turned back into) the original object.

For example, if you have an object that has pointers to several other objects, we need to store all of this instead of just being able to store the pointers themselves. Pickle is an example of a library in python that is used to serialize and deserialize data.