---
title: How to Push Code for Production
tree_state: 🌱
---

Make pull requests small so that they are easy to review and only include 1 key feature at a time.
1. When making changes switch to a different branch with this
```git checkout -b <branchname>```
Typically a branch name will be related to the change you are making but it doesn't really matter.
2. Add and Commit your changes normally. When you push your changes from a new branch you must run
```git push --set-upstream origin <branchname>```
If you have already pushed from the branch then you can push normally
3. Go to the github repository after pushing and click submit a new pull request
4. Write what you changed in the comments and add a relevant reviewer to process your push.


### Naming Conventions
`fix/<thing you fixed or bug>`
`feature/<new thing you implemented>`
`experiment/<thing you're experimenting with>`