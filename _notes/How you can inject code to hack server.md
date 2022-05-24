---
author: Michael
catalog: true
date: 2022-04-14
header_img: /img/in-post/new_header1.jpg
header_mask: rgba(40, 57, 101, .4)
header_style: image
subtitle: No subtitle
tags:
- notes
title: How you can inject code to hack server
tree_state: 🌱
---

A little while ago there was a security vulnerability discovered in specific versions of the Apache Log4j software. This software is used in a ton of packages, so a lot of people didn't even realize that they were using log4j.

One way that  hackers can figure out if a server is running a specific version of software is in the header name of the url. 

They can also find a list of vulnerabilities for specific software in CVE logs.

After learning this, the hackers can inject some code into the server and take control. 