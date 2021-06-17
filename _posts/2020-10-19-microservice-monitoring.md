---
layout: post
title: Microservice monitoring - Log centralization
subtitle: Monitoring containerized microservices with a centralized logging architecture.
gh-repo: krakenon/blogs
gh-badge: [star, fork, follow]
tags: [multi-thread, multi, threading]
author: duy_luong
comments: true
---

## Problems

We all know importance of logging in applications but it is even more crucial in distributed systems. There are challenges of logging in microservices architectures.

As the amount of services in a microservice architecture rises, complexity naturally also rises. Bugs and individual service failures can be very tricky to deal with and having to spend hours digging deep to find the root of an unnamed error can be a daunting and unproductive task.And they get even more complicated when one or more services fail.

- Which service failed?
- Why?
- And under what circumstances?

To effectively deal with the challenges of system errors, request chain breakdowns, or even simply to stay on top of your system architecture, logging is a vital tool. It is undeniable that it is the cornerstone of maintaining and debugging your app efficiently. All these questions are hard to answer if you don’t have good, meaningful logs.

## Why we need a Centralized Log Management (CLM) for microservice architecture?

![microservice architecture](/img/microservices-architecture.png)

In the microservice pattern, thousands of services operate independently and are distributed across many different infrastructures with each service having different types of logs. Therefore we need a central control of these logs synchronously and centrally manage them. Ensure that when any errors arise, we can trace them and offer a quick and thorough solution.

In order to ease this entire process, many solutions such as a Centralized Log Management (CLM) solution comes into the picture.
