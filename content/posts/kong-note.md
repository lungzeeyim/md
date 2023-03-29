---
title: "Kong Study Note"
date: 2023-03-28T16:04:06+08:00
draft: true
---
# Getting Started
Access the Lab Terminal: https://18080-0-bc1a02b5.labs.konghq.com/
Access Kong Manager: https://8002-0-bc1a02b5.labs.konghq.com/
Gateway Data URL: https://8000-0-bc1a02b5.labs.konghq.com
Kong Admin API URL: https://8001-0-bc1a02b5.labs.konghq.com

# Kong Gateway Fundamentals
### Kong Manager
Kong Manager is browser-based UI for monitoring and configuring gateway
- configure routes and services
- enable/disable plugins
- monitoring
- manage users' RBAC (Role-Based Access Control)

Default port for Kong Manager's user interface:
- 8002 HTTP
- 8445 HTTPS

`Delegated workspaces 受委托空间` allow teams of admins to 
share the same `Kong cluster 集群` 
and only interact with entities relevant to them 
using Role Based Access Control (RBAC).

### Service and Routes
A Service is an entity representing an external upstream API or micro-service
The main attribute of a Service is its URL, where Kong should proxy traffic to.  

We can add a route to a service for accessing to it.
Service represents the back-end API.
A route defines what is exposed to clients.
After reaching Kong gateway, routes determine how requests are sent to services.  

```
Service: httpbin
name: foo-route
Protocol(s): http
Host(s): myfrontend.com
Method(s): GET
Path(s): /foo
```
Kong gateway will accept requests of `front-end.com/foo`.
And Gateway will map these requests to httpbin service  

Verify forwarding a request
```
http --proxy http://localhost:8000/ http://myfrontend.com/foo
```

### Plugins
Run plugins to transform request/response or perform (运行) a variety of (各种) other tasks.

Add features to your API:
- authentication
- rate limit
- logging
- transformations

Plugins will check to make sure
- Request has a proper API key
    - not have key: `401 error`
- Isn't subject (受限) to rate limits
    - exceed number of requests: `429 error`
- Transform request
    - ex. Add header

Enable a Plugin for Authentication  

Verify that the plugin is properly configured
- we need to pass user (i.e. consumer) credentials! `i.e. = that is`


### Consumers
Consumers are clients to Kong's Service.
Let you control who can access APIs.
Let you report on traffic (报告流量状况) using logging plugins and Kong Vitals (命脉).

Task:
1. Enable a Consumer









