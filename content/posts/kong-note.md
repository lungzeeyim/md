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
2. Provision key credentials (提供关键凭证)for Consumer 'Joe'
3. Verify Consumer credentials are valid & the Auth plugin is properly configured

### Upstreams
Two methods for load balancing (负载平衡)
1. DNS-based
2. ring-balancer

Virtual IPs of a service/route is behind `load balancer`

### Recap
1. upstream API (service) called "httpbin" and its URL: httpbin.org/anything
2. route "myfrontend.com/foo" pointing to this service
3. authentication plugin for requiring API Keys
4. consumer (user) with valid credentials

`Refer to (参考)` the documentation `as (当)` you perform the following lab.

### Monitoring with Vitals
- Use Kong Vitals (Vitals) to monitor Kong Gateway health and performance. And understand API `transaction (事务)`.
- visual API analytics
- `pinpoint (精确定位) anomalies (异常)` in real time

Use Kong Admin API to access Vitals
- visualizations including dashboarding of Vitals data `alongside (与)` data from other system.

Kong Vitals:
1. `ramp up (增加)` the number of requests for user 'Joe'
2. view 4XX errors and `traffic spike (流量急升)`
3. reconfigure the rate limiting plugin to exclude user 'Joe'
4. verify reduced errors

### Kong Admin API
Edit configuration through Kong Admin API

Kong comes with an internal RESTful Admin API for administration purposes.
- API is for internal use
- API has full control over Kong
- `care should be taken (小心)`, avoid `undue (不适当的)` public exposure of APIs

Will `go through (通过)` and explain the `various (各种) component and functionality of Kong.

Verify Kong Admin API is Running
```
http GET http://localhost:8001 --headers
```







































