---
title: What is Elasticsearch
tree_state: 🌱
---

Elasticsearch is an open source a search engine that people use when building their web applications. 

You need to run elasticsearch on a server for it to work. You can do this on your own server, using AWS, or the hosting service the creators of Elasticsearch have developed.
- **Algolia** is an alternative search platform (only offered using their server hosting) that's easier to setup but offers less customizability


### Tools on Top of Elasticseach
There are several tools built on top of Elasticsearch to integrate with it
- Let's say your application is a combination of a bunch of different services with very different logging information. **Logstash** is a platform that can aggregate all your logs into one central place and then store it so that your logs are searchable with Elasticsearch.
- **Kibana** is a dashboard that can be used to visualize information about the data you have stored in elasticsearch (this includes your logs if you use Logstash)
- **Beats** is a more minor extension that arose due to issues in Logstash's performance. Beats are made to more efficiently extract specific kinds (depends on which beat you're using) of logging data to then be sent to Logstash.