---
title: What is OAuth
tree_state: 🌱
---

There was a fundamental isse with “How can I allow an app to access my data without necessarily giving it my password?” The concept of a **delegated authority** allows the owner of a set of resources (me or you) to delegate access to some of those resources to a designated client application, without enabling the client application to impersonate the user. In other words, we want an app to know that we are the right person in the account/app, without giving them access to our passwords/data when we log in.

OAuth is a delegated authorization framework for REST/APIs. It enables apps to obtain limited access (scopes) to a user’s data without giving away a user’s password.

OAuth decouples **authentication** from **authorization** and supports multiple use cases addressing different device capabilities.
- You can think of this like hotel key cards, but for apps. If you have a hotel key card, you can get access to your room. How do you get a hotel key card? You have to do an authentication process at the front desk to get it. After authenticating and obtaining the key card, you can access resources across the hotel.

To break it down simply, OAuth is where:
1.  App requests authorization from User
2.  User authorizes App and delivers proof
3.  App presents proof of authorization to server to get a Token
4.  Token is restricted to only access what the User authorized for the specific App

https://developer.okta.com/blog/2017/06/21/what-the-heck-is-oauth