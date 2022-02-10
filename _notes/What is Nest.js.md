---
title: What is Nest.js
tree_state: 🌱
---

Nestjs is a framework for building Node.js server-side applications. Documentation is here: https://docs.nestjs.com/

Nestjs handles a lot of the server-side code for you to create routes for specific tasks when making your app's API.

# Nestjs Components

## Controllers
Controllers are responsible for handling incoming **requests** and returning **responses** to the client. You use Nestjs **decorators** to associate specific classes with required metadata and enable Nest to create a routing map (tie requests to the corresponding controllers).

Controllers should handle HTTP requests and delegate more complex tasks to **providers**.

## Providers
Providers in Nest are used to create services, factories, helpers, and more that can be injected into controllers and other providers using Nest’s built-in **dependency injection**. Providers probably contain most of your code and core functionality.

When you have defined a provider, and you have a consumer of that service (perhaps a controller or maybe even another provider), you need to register the service with Nest so that it can perform the dependency injection. You do this by adding the provider and controller to the corresponding **module** for this functionality/workflow.

## Modules
Modules are like containers for a cohesive block of code dedicated to a workflow, or closely related set of capabilities. When creating a module Nestjs takes in the service providers and controllers for the module. It also takes a the list of imported modules that export the providers which are required in this module.

Each application has at least one module, a **root module**. The root module is the starting point Nest uses to build the **application graph** - the internal data structure Nest uses to resolve module and provider relationships and dependencies.