---
title: How is Unit Testing Done
tree_state: 🌱
---

- When running your tests, you want to see what parts of your code are run and not run across all your tests. For example, if you have code that is never called across your tests, you don't know what will happen when it is called in production.
- When testing your code, you should remove the dependencies for different parts of the application, to test each part of the application separately.
	- Useful example to explain is here https://stackoverflow.com/questions/2665812/what-is-mocking#answer-40244095:~:text=Real%20world%20coding%20Example%3A