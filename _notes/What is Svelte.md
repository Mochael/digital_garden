---
title: What is Svelte
tree_state: 🌱
---

## Svelte
Svelte is a front end javascript framework that keeps your code very similar to regular javascript. In frameworks like React, they store a representation of the UI that is kept in memory (**virtual DOM**) and updated every time your app's state changes. React's job is to **reconcile** the new updated virtual DOM with the “real” DOM, which means it needs to figure out what changes are necessary and apply them to the real DOM. This takes a bit of time because you need to iterate through the attributes of the element that changed, and see exactly which part of it needs to be changed. There is also a lot of opportunity to cause some React attributes to unnecessarily re-render, which hurts your apps performance even more. All this being said, React and other frameworks that use a virtual DOM are still pretty fast. 

On the other hand, the Svelte compiler knows at build time how things could change in your app, rather than finding out what was changed during run time. Svelte's compile step pre-converts your app into vanilla (highly optimized) JavaScript with no Svelte runtime, framework, or library present after the build process.

In Svelte can insert javascript variables into HTML by using curly braces `{variable_name}` anywhere in the HTML markup.

**Sapper** is Svelte's version of Next.js ([[What is Next.js]]).