---
title: Methodology for Managing Web Apps
tree_state: 🌱
---

Notes are from https://12factor.net/

1. Each application should only have 1 codebase, but a single codebase can have many running instances on different branches.
2. Packages for an app should be scoped into the directory of the app (known as “vendoring” or “bundling”), instead of being system-wide. You should use a *dependency declaration* tool for installing dependencies and  a *dependency isolation* tool during execution to ensure that no implicit dependencies “leak in” from the surrounding system. Examples:
	- `Bundler` in Ruby gives `Gemfile` for dependency declaration and `bundle exec` for dependency isolation
	- In Python `Pip` is used for dependency declaration and `virtualenv` for dependency isolation
	- So when a new developer gets the app they should only need the language runtime and dependency manager installed as prerequisites. Then they can just install everything via a *build command*
3. There should be a **strict separation of config from code**. Config being: credentials to external services, deploy info like the host name of the deploy, etc. The codebase should be able to be made open source at any moment, without compromising any credentials. Config information should be stored in **environment variables** which are language and OS agnostic standard. Also, config variables should be independently managed for each deploy.
4. An app should be able to swap out a local service (like a MySQL database) with one managed by a third party (like Amazon RDS) without making any changes to the app’s code. A *backing service* is any service that your app uses over the network as part of its normal operation. Your app should make no distinction between local and third party backing services. Each backing service should be treated like a resource that can be attached to and detached from deploys at will. All that you might need to change is some config info, but no code.
5. New builds are initiated by the app’s developers whenever new code is deployed. Every release should always have a unique release ID or an incrementing number, releases should be an append-only ledger, and a release cannot be mutated once it is created. Any change must create a new release. Runtime execution should be able to happen automatically in cases such as a server reboot.
6. The app is executed in the execution environment as one or more *processes*, where processes are stateless and share-nothing. Any data that needs to persist must be stored in a stateful backing service, like a database. Some web systems rely on caching user session data in memory of the app’s process and expecting future requests from the same visitor to be routed to the same process, but instead you should store session state data is a good candidate for in a datastore that offers time-expiration, such as [Memcached](http://memcached.org/) or [Redis](http://redis.io/).
7. Don't entirely understand this one. Seems like the main takeaway is that the web app needs to bind to a port to listen to requests coming in on that port.
8. 