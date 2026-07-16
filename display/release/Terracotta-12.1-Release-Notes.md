---
title:  Terracotta 12.1 Release Notes  
lang: en
layout: page
keywords:
space: current
sidebar: lb2_sidebar
permalink: /display/release/Terracotta+12.1+Release+Notes.html
summary:
---

Terracotta provides distributed in-memory operational data storage and caching for highly concurrent use cases requiring low and predictable latency.

The Terracotta 12.1.x Enterprise Edition offering includes the following:

   *  Distributed Caching capabilities via Java's most widely used cache, Ehcache 12.1.x API 
   *  Distributed In-Memory Operational Data Storage capabilities via the TCStore API
   *  Distributed In-Memory Data Management with fault-tolerance, and both horizontal and vertial scaling via Terracotta Server
   *  In memory off-heap storage - take advantage of all the RAM in your server and your client applications without GC pauses
   *  Terracotta Management Console for monitoring and managing your Terracotta cluster, and the workload that you've thrown at it

------

<br>

Document Contents

* TOC
{:toc}

<br>

# Current Release
------------------
Terracotta 12.1 (May 2026) is the latest release. It includes Ehcache 12.1.0.

Fixes are cumulative from version to version.

<br>

# Feature Highlights
------------------
The Terracotta 12.1 release builds upon the enterprise readiness features and analytical capabilities of past releases, by improving operational usability and performance. Some of the notable features of Terracotta 12.1 include:

* Branding for IBM
* Support for Java 21
* Improved security

<br>

# Summary of Changes 12.1
-----------------------
### 12.1.0.1
* Release Date: 2026/05/22
* Resolved
  * Internal maintenance items
* Security Updates to Third Party Libraries
  * Update base docker image version
  * jakarta.annotation to 6.0
  * jackson to 2.21.4
  * commons-logging to 1.3.6
  * prometheus to 1.4.3
  * smallrye to 2.14.0
  * undertow to 2.4.0.Final
  * jakarta.annotation-api to 3.0.0
  * jakarta.servlet-api to 6.1.0
  * jakarta.validation-api to 3.1.1
  * jakarta.websocket-api to 2.2.0
  * accessors-smart to 2.6.0
  * json-smart to 2.6.0
  * Calcite to 1.42.0
  * parquet to 1.17.1
  * jboss-threads to 3.9.2
  * wildfly-common to 2.0.1
  * snakeyaml to 2.5
  * Spring Boot to 4.0.6
  * Spring Security to 7.0.5
  * Spring to 7.0.7

### 12.1.0.2
* Release Date: 2026/07/16
* Resolved
  * Internal maintenance items.
* Security Updates to Third Party Libraries
  * Update docker base image version


<!-- Next entrypoint --> 

<br>

# Notes
-------
* Terracotta BigMemory 4.4.1.x and Terracotta 11.1.x clients may be used simultaneously in the same application by ensuring ClassLoader isolation when initializing at least one of the clients.
<br>
