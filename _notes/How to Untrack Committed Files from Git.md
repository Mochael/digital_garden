---
title: How to Untrack Committed Files from Git
tree_state: 🌱
---

1. Run the command
```
git filter-branch --index-filter "git rm -rf --cached --ignore-unmatch <filepath (or folderpath)>" HEAD
```
2. Make sure the files are now in your `.gitignore` before you stage and then commit again