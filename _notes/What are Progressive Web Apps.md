---
title: What are Progressive Web Apps
tree_state: 🌱
---

## Progressive Web Apps
Not really a whole new technology: it's just a web app that abides by a few principles:
- Secure Contexts with HTTPS (see [[What is HTTPS]]):
	- The web application must be served over a secure network.
- Service workers (see [[What are Javascript Workers]]):
	- handle caching of network requests so that some of your requests can be filled locally without internet access, allowing your web app to have some offline functionality
- Manifest file:
	- The Manifest file is a simple JSON file that gives you the ability to control how your app appears to the user. It describes the name of the app, the start URL, icons, and all of the other details necessary to transform the website into an app-like format.

[Google Lighthouse](https://developers.google.com/web/tools/lighthouse) is a tool you can use in your browser while developing a PWA to check your progress on implementing the required features.