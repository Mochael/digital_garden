---
title: JAMStack
tree_state: 🌱
---

## Good Explanation
https://jamstack.org/what-is-jamstack/


## When you would want to use the JAMStack Architecture
If you are building an application where the html files won't be changing that frequently JAMStack works well because the pre-rendered files you are sending users through the CDN (Content Delivery Network) don't need to be constantly re-rendered and re-distributed.
**When to Use JAMStack**
Let's say we are building an ecommerce website where we occassionally update what items we are selling on our store. JAMStack would suite this use case very well because the pages for each product can be prerendered and distributed via the CDN. This will be extremely fast because the pages are all rendered already and being sent to you through a closeby server (through the CDN). There are also fewer security vulnerabilities since users will either only have access to the static site or limited access to interface with your backend through a small number of API calls.
**When JAMStack may not be as useful**
Now suppose we are building an online note taking application. The content is dynamic because users constantly add information to and from their notes and there are millions of users so we need to store millions and millions of notes pages. It would be very inefficient to store each of these pre-rendered pages with a CDN. A CDN is meant to optimize speed of serving users webpages, it is not meant to function as an entire database itself for all your content. In this case it would be better to just store all our notes and their related files (i.e. images, video, etc) in database that we can query from and then render to the user.