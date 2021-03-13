---
title: How to Set a Specific Branch to Track a Specific Remote Branch with Git 
tree_state: 🌱
---

How to pull form specific branch without automatically tracking it:
```
git pull origin <remote_branch_name>
```

How to set local branch to track remote branch
```
git branch --set-upstream-to=origin/<remote_branch_name> <local_branch_name>
```