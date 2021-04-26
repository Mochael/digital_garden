---
title: What are Javascript Workers
tree_state: 🌱
---

A worker is a script (separate Javascript file) that runs on a thread separate to the browser’s main thread. If you think about your typical Javascript file that is included in your HTML document via a `<script>` tag, that runs on the main thread.

Workers do not have access to the DOM, which means that any information they want to send must be passed between the worker and the main script using post messages.

Workers are terminated when not in use, so you cannot rely on global state for your service workers. However, you can have workers fetch information from client-side storage (using the IndexedDB API for example).

## Web Workers

Web workers are the most general purpose type of worker, without a specific use case. They are just used to offload the processing of some feature from the main thread. 

Web workers are created using the `Web Workers API`.


## Service Workers

Service workers are a type of worker that serve the explicit purpose of being an intermediary between the browser and the network and/or cache. Once they are installed and activated, service workers are able to intercept any network requests made from the main document. Once intercepted, a service worker can, for example, respond by returning a document from the cache instead of going to the network, thereby allowing web applications to function offline!


## Worklets

Worklets enable running custom code in various parts of the browser’s rendering process. This [article](https://bitsofco.de/understanding-the-critical-rendering-path/) explains how browsers render web pages. For example, during the page rendering process when the browser is applying the styles to each HTML element, we can use worklets to inject custom images into anywhere CSS expects an images.