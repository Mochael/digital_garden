---
title: What is WebAssembly
tree_state: 🌱
---

Really helpful video:
https://www.youtube.com/watch?v=3sU557ZKjUs


## Introducing the Problem
Way back in the day when C was built to compile into assembly code, there was the issue that different microprocessors had different assembly commands. So, instead of creating a new C compiler for every microprocessor, we abstracted a "virtual" microprocessor that would have limited functionality, but would function properly across all microprocessors. This "virtual" microprocessor would have it's own compiler to compile C into it's own version of bytecode, which it could then translate into something understandable by the actual microprocessor.

With web browsers we have the same problem where Internet Explorer processes code differently than Chrome and other browsers (for example some code may work on Chrome but not on Safari). WebAssembly works in the same way that we compiled C to processors. We write code in some language C/Rust/etc which is the compiled into web assembly bytecode which can be understood by any browser.


## How WebAssembly Works

Currently, Web Assembly bytecode cannot directly interact with the DOM (your html): it must go through javascript. When you write code in Rust/C and compile it, it creates a **WebAssembly module**. A **WebAssembly module**  stores a list of functions you implemented in your Rust/C code in the form of bytecode. So, in a javascript file you can basically import these functions and use them.

- I think one of the main uses of WebAssembly will be by package developers, whose libraries are normally used by importing functions and applying them yourself.


## Programming in WebAssembly
WebAssembly has its own assembly language called **Web Assembly Text Format** that you can use.

Rust has the best WebAssembly support though: when you install Rust it comes with WebAssembly out of the box.


## Web Assembly Outside the Web
People have develop **WASI**, a system interface that let's you run WebAssembly outside the web.


## Content delivery networks (CDNs) with WebAssembly

Cloudflare and Fastly have developed huge CDNs spanning the entire world by storing copies of your website in data centers across the world and then using workers to send your website's code to users. Cloudflare has machines distributed across the world host an instance of the Workers' runtime, which can compile Javascript and use common APIs.

Cloudflare has been implementing the functionality to  compile workers' functions written in any language to WebAssembly. This way the machines used for compute won't even need to use these runtimes anymore, they can just run the WebAssembly.