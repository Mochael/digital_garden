---
title: Client vs Server Side Rendering
tree_state: 🌱
---

Server side rendering is where javascript is executed on the server so that it turns the javascript code into HTML (rendering it). You then send the HTML file back to the client (a user's computer)
Client side rendering is where the server sends javascript to the client which then runs the javascript locally (executing whatever APIs are used to fetch data back from the server) to turn the javascript into HTML

## Why Server can be > Client
1. Client side 1st needs to be sent javascript
2. Then client has to run the javascript on their computer
3. the javascript will probably make API calls back to your server to fetch the dynamic content which will then have to be sent back to the client
4. also people's local computers are generally slower than a server anyways