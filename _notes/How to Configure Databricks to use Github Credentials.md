---
title: How to Configure Databricks to use Github Credentials
tree_state: 🌱
---


1. Find your git personal access token (what you use as your password to log in to GitHub)
2. Hit top right corner of databricks UI and go to User Settings-> Git integration
   1. Input your personal git access token into this
3. Now go to User Settings-> Access Tokens, generate a new token (name doesn't matter), and copy it somewhere
4. Create a new databricks notebook and open it up
   1. Select a cluster (if you haven't already) from the top left of screen and start the cluster
5. Locally open a terminal and do all the following in that terminal:
   1. run `pip install databricks-cli`
   2. `databricks configure --token` 
      1. Copy in the link to databricks (must start with https:// and ends in .com).
      2. paste in the token that you generated in Databricks Access Tokens
   3. Create a scope with `databricks secrets create-scope --scope <scope-name>`
   4. run this `databricks secrets put --scope <scope_name> --key <key_name>`
   5. Put git personal access token into the text file, then save and exit vim
7. You should be all set!

To clone a repository to a databricks notebook type the following into databricks (substituting `<scope_name>`, `<key_name>`, and  `<branch_name>` with what's appropriate where `<branch_name>` is the name of the GitHub repo's branch you want to use.

```
token = dbutils.secrets.get(scope=<scope_name>, key=<key_name>)
%pip install --no-dependencies git+https://$token@github.com/<org_name>/<repo_name>@<branch_name>#egg=<pkg_name>
```

