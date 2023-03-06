# Week 2 — Distributed Tracing

Observability is the ability to measure a system's current state based on the data it generates.
The three critical pillars are Metrics, Traces and Logs.

Distributed tracing is a method of tracking application requests as they flow from frontend devices to backend services and databases. Distributed tracing is a technique used to monitor and observe requests as they flow through distributed services or microservices-based applications. Use distributed tracing to troubleshoot requests that exhibit high latency or errors.

### Honeycomb: Observability for Distributed Services
Honeycomb is a full-stack cloud-based observability tool with support for events, logs, and traces. Honeycomb provides an easy-to-use distributed tracing solution.
Some of the key features of the Honeycomb distributed tracing tool includes:

Quickly diagnose bottlenecks and optimize performance with a waterfall view to understand how your system is processing service requests
Full-text search over trace spans and toggle to collapse and expand sections of trace waterfalls
Provides Honeycomb beelines to automatically define key pieces of trace data like serviceName, name, timestamp, duration, traceID, etc.

#### Code instrumentation
Code instrumentation to emit telemetry data is the first step toward achieving observability. Rather than instrumenting with proprietary libraries or agents that lock you into one particular vendor, you can use OpenTelemetry to collect, generate and export telemetry data into any backend system you choose, including Honeycomb.

#### OpenTelemetry
OpenTelemetry (or “OTel”) is a collection of open-source tools, APIs, and SDKs to generate, collect, and export telemetry data such as traces, metrics, and logs. It integrates with a wide variety of libraries and frameworks in various languages, many of which include automatic instrumentation out-of-the-box. As an open source and vendor-neutral project, OTel allows you to send that data to multiple backends and avoid vendor lock-in.

Instrumented backend-flask service with OpenTelemetry to create traces in Honeycomb.
Error when instrumenting using OTel for backend-flask servce.

![image](https://user-images.githubusercontent.com/123596308/223039989-6205a508-1ed8-494a-9c44-8428044991b7.png)

Homeycomb's 

![image](https://user-images.githubusercontent.com/123596308/223041531-b0a5b30e-60f5-4917-9c7f-5fa700fc82ac.png)

### AWS X-Ray 

AWS X-Ray is a service that collects data about requests that a application serves, and provides tools that can be used to view, filter, and gain insights into that data to identify issues and opportunities for optimization. For any traced request to your application, you can see detailed information not only about the request and response, but also about calls that your application makes to downstream AWS resources, microservices, databases, and web APIs.

#### Instrumentation with AWS X-Ray SDK
Instead of OpenTelemetry installed AWS X-Ray SDK and  instumented the backend-flask service. 
Instead of sending trace data directly to X-Ray, the SDK sends JSON segment documents to a daemon process listening for UDP traffic. The X-Ray daemon buffers segments in a queue and uploads them to X-Ray in batches.
Created crudder group in AWS X-Ray and filtered by backend-flask service using 
aws xray create-group \
   --group-name "Cruddur" \
   --filter-expression "service(\"backend-flask\")"
Also created sampling rule with a json file and a  AWS-XRay-Deamon Service via Docker Compose file.

### AWS CloudWatch Logs

With CloudWatch Logs enables we can centralize the logs from all our systems, applications, and AWS services that we use, in a single, highly scalable service.
Installed WatchTower and wrote a custom logger to send application log data to CloudWatch Log group.

### Rollbar
Rollbar is a cloud-based bug tracking and monitoring solution. Rollbar is an Error Logging and Tracking Service for teams.
Installed Rollbar and instrumented for logging errors and created an endpoint for testing rollbar.
Triggered error 

![image](https://user-images.githubusercontent.com/123596308/223048509-66e319ed-9775-4fe5-8f25-fa4be685b43d.png)

Endpoint

![image](https://user-images.githubusercontent.com/123596308/223049133-122ddb49-2656-4893-b03e-5a6998593180.png)


Endpoint and Errors in Rollbar grouped on severity

![image](https://user-images.githubusercontent.com/123596308/223048925-3240ddb4-a0f5-41ea-aa99-17754943a8b9.png)

Stack Trace

![image](https://user-images.githubusercontent.com/123596308/223049570-39f528e3-b74a-40c0-aebd-4ad3977f9313.png)









