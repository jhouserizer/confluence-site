---
title:  BigMemory Max 4.5.1 Release Notes and Notifications
lang: en
layout: page
keywords:
space: current
sidebar: lb2_sidebar
permalink: /display/release/BigMemory+Max+4.5.1.html
summary:
---

BigMemory Max delivers ultrafast access to hundreds of terabytes of in-memory data. BigMemory snaps into enterprise applications to deliver unmatched performance at any scale.

BigMemory Max supports a distributed in-memory data-storage topology, which enables the sharing of data among multiple caches and in-memory data stores in multiple JVMs. It uses a Terracotta Server Array to manage data that is shared by multiple application nodes in a cluster.

The Ehcache 2.12.1.x API can be used with BigMemory Max 4.4.1.x as a general-purpose cache/in-memory data store or a second-level cache for Hibernate. You can additionally integrate it with third-party products such as Google App Engine, Spring, and others.

------

<br>

Document Contents

* TOC
{:toc}

<br>

## Current Release
------------------
BigMemory Max 4.5.1 (May 2026) is the latest release. It includes Ehcache 2.12.1.

Fixes are cumulative from version to version within the BigMemory Max 4.5.1 product line.

<br>

## Feature Highlights
-------------------
BigMemory Max 4.5.1 introduced the following new capabilities:

* Rebranding for IBM
* Support for Java 21
* Security enhancements and bug fixes
* Contains all features and functionality included in [BigMemory Max 4.4.x](https://confluence.terracotta.org/display/release/BigMemory+Max+4.4)

<br>

# Summary of Changes 4.4.5.1
-----------------------
### 4.4.5.1
* Release Date: 2026/06/22
* Resolved
  * Internal maintenance items
* Security Updates to Third Party Libraries
  * Update base docker image version 
  * [TAB-10019] [4.4.0] Update logback to 1.5.34 due to CVE-2026-10532, CVE-2026-9828  
  * [TAB-10031] Update shiro to 2.2.0 due to CVE-2026-43827, CVE-2026-43828, CVE-2026-44598, CVE-2026-48589

### 4.4.5.2
* Release Date: 2026/07/16
* Resolved
  * Internal maintenance items
* Security Updates to Third Party Libraries
  * Update base docker image version 
  * [TAB-10031] Update shiro to 2.2.1 due to CVE-2026-43827, CVE-2026-43828, CVE-2026-44598, CVE-2026-48589
  * [TAB-10051] Update jackson-databind due to CVE-2026-54512, CVE-2026-54513, CVE-2026-54514, CVE-2026-54515  
  * shiro to 2.2.1
  * jackson-databind to 2.21.5
 
    
<!-- Next entrypoint --> 

<br>

# Notes
-------
* Terracotta BigMemory 4.5.1.x and Terracotta 12.1.x clients may be used simultaneously in the same application by ensuring ClassLoader isolation when initializing at least one of the clients.
<br>


# Important Upgrade Information
-------
The following information is contained in the readme.txt file included with each fix release and should be reviewed prior to applying any fix.
<br>
```
8.0 Installation

8.1 Shut down the server array. A safe shutdown procedure is as follows.

    a. Shut down the mirror servers using the stop-tc-server script. 
       If you are using a wrapper solution to manage the mirror servers, execute the wrapper shut
       down command to shut down the mirror servers instead of using the stop-tc-server script.

    b. Shut down the clients. A terracotta client will shut down when you shut down your application.

    c. Shut down the active servers using the stop-tc-server script.
       If you are using a wrapper solution to manage the servers, execute the wrapper shut down
       command to shut down the servers instead of using the stop-tc-server script.

8.2 This fix overwrites server scripts,wrapper configuration files and default tc-config.xml. If
    you have any custom settings defined on those files (ex:MaxDirectMemorySize), then you need to
    restore those settings back after applying the fix.

8.3 Install using Update Manager. For instructions, see the documentation at
    https://docs.webmethods.io/.

8.4 The upgrade of the 3rd party library Shiro may create an issue for some users that will require
    a manual configuration change to the "shiro.ini" found in the ".tc/mgmt" directory of the
    user's home folder (the user that the TMS/TMC process runs as ~/.tc/mgmt/shiro.ini). Edit this
    file and restart the TMS/TMC.
     
    a. Blank browser page or a message from the browser indicating too many redirects, or similar.
       In [urls] section of file ~/.tc/mgmt/shiro.ini, locate the line in the that reads
       "/login.jsp = authc". Immediately above that line add the three following lines:

       /401.jsp = anon
       /403.jsp = anon
       /404.html = anon
      
       In the [main] section of file ~/.tc/mgmt/shiro.ini, add the following line:
      
       [main]
       shiro.filterOncePerRequest=true
   
    b. URLs containing semi-colon are blocked and 400 client error is thrown. 
       In the [main] section of file ~/.tc/mgmt/shiro.ini, add the following two lines to the top
       of the section:

       [main]
       invalidRequest = org.apache.shiro.web.filter.InvalidRequestFilter
       invalidRequest.blockSemicolon = false

    c. Previously, secure cookies in TMS were enabled by default, working only with TLS-secured 
       connections or localhost requests. Remote HTTP access required adding the following line to 
       the ~/.tc/mgmt/shiro.ini file:
       
       [main]
       securityManager.sessionManager.sessionIdCookie.secure = false
       
       The default value for this setting is now set to false. A restart of the TMS for changes
       to take effect.

8.5 The upgrade of the 3rd party library Jetty to v12+ will result in the following configuration changes:

    To allow an SSL connection from the managed agent, the SSL connector must be configured. If the TMS is deployed
    with the provided Jetty web server, add the following to /tools/management-console/etc/start.d/ssl.ini
    (in the BigMemory kit) as shown:

       jetty.sslContext.keyStorePath=etc/dev-keystore.jks
       jetty.sslContext.trustStorePath=etc/dev-keystore.jks
       jetty.sslContext.keyStorePassword=terracotta
       jetty.sslContext.trustStorePassword=terracotta
       jetty.sslContext.keyManagerPassword=terracotta

9.0 Uninstallation

9.1 Shut down the server array. A safe shutdown procedure is as follows.

    a. Shut down the mirror servers using the stop-tc-server script. 
       If you are using a wrapper solution to manage the mirror servers, execute the wrapper shut
       down command to shut down the mirror servers instead of using the stop-tc-server script.

    b. Shut down the clients. A Terracotta client will shut down when you shut down your application.

    c. Shut down the active servers using the stop-tc-server script.
       If you are using a wrapper solution to manage the servers, execute the wrapper shut down
       command to shut down the servers instead of using the stop-tc-server script.

9.2 Uninstall using Update Manager. For instructions, see the documentation at
    https://docs.webmethods.io/.
```
	  
<br>
