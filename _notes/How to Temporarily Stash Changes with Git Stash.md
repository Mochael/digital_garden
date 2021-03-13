---
title: How to Temporarily Stash Changes with Git Stash
tree_state: 🌱
---

`git stash` temporarily shelves (or stashes) changes you've made to your working copy so you can work on something else, and then come back and re-apply them later on. Stashing is handy if you need to quickly switch context and work on something else, but you're mid-way through a code change and aren't quite ready to commit.

The `git stash` command takes your uncommitted changes (both staged and unstaged), saves them away for later use, and then reverts them from your working copy. 
- Adding the `-u`option (or `--include-untracked`) tells git stash to also stash your untracked files
- Adding the `-a`option (or `-all`) tells git stash to also stash ignored files
- `git stash save "message"` allows you to specify a message corresponding to a specific stash

## How to Get Back Stashed Code
- `git stash list` allows you to list out all the different stashes you've made
- `git stash pop` reapplies previously stashed changes but removes the changes from your stash, so they are no longer stashed.
	- defaultly applies the most recently stashed code
- `git stash apply` reapplies previously stashed changes without removing the code from your stash
- You can choose a specific version to reapply with `git stash pop stash@{2}` where `stash@{2}` represents the identifier for which stash to pop