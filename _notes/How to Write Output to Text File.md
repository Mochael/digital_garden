---
title: How to Write Output to Text File
tree_state: 🌱
---

`SomeCommand > SomeFile.txt` overwrites `SomeFile.txt` with the output from `SomeCommand`

`SomeCommand >> SomeFile.txt` appends the output from `SomeCommand` to the text file

`SomeCommand &> SomeFile.txt` overwrites the output as well as the `stderr` output from `SomeCommand` to the text file