---
title: How to Access a Previous Commit with Git
tree_state: 🌱
---

`git revert <hash-or-ref>`
- This command creates a new commit that undoes the changes from a previous commit. This command adds new history to the project (it doesn't modify existing history).

`git checkout -b <branch_name> <hash-or-ref>`
- This command creates a new branch that points to a previous commit of yours.
- Using `git checkout <hash-or-ref>` instead would set you on a **detached HEAD**. This is because it would set the **HEAD** (the part of git that tracks what your current working directory should match) to point directly to a commit rather than a separate branch. So, as soon as you checkout a new branch or tag, the detached commits will be “lost” (because HEAD has moved)
- If you have modified a file in your working tree, but haven't committed the change, then you can use git checkout to checkout a fresh-from-repository copy of the file.

## Use `git log` to get the hash to a previous commit


## Merging
Running `git merge <branch_to_be_merged_in_to_current_branch>` merges the branch you put in the argument into the current branch you are located in.