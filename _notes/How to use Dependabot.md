---
title: How to use Dependabot
tree_state: 🌱
---

You can configure Dependabot to automatically submit PRs to merge in updates to your packages. It works for many different languages and package managers: pip (python), npm (javascript), docker, etc.

To set it up you just need to create a `dependabot.yml` file in your `.github` directory that looks like this:

```
version: 2
updates:
	- package-ecosystem: "pip"
		directory: "/"
		schedule:
			interval: "weekly"
		open-pull-requests-limit: 10
```