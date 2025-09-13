---
title: "Tracezip: Efficient Distributed Tracing via Trace Compression"
collection: publications
category: manuscripts
permalink: /publication/tracezip
excerpt: 'Compressing trace data with SRT.'
date: 2009-10-01
venue: 'Proceedings of the ACM on Software Engineering, Volume 2, Issue ISSTA'
paperurl: 'https://dl.acm.org/doi/10.1145/3728888'
---
Distributed tracing serves as a fundamental building block in the monitoring and testing of cloud service systems. To reduce computational and storage overheads, the de facto practice is to capture fewer traces via sampling. However, existing work faces a trade-off between the completeness of tracing and system overhead. On one hand, head-based sampling indiscriminately selects requests to trace when they enter the system, which may miss critical events. On the other hand, tail-based sampling first captures all requests and then selectively persists the edge-case traces, which entails the overheads related to trace collection and ingestion. Taking a different path, we propose Tracezip in this paper to enhance the efficiency of distributed tracing via trace compression. Our key insight is that there exists significant redundancy among traces, which results in repetitive transmission of identical data between services and the backend. We design a new data structure named Span Retrieval Tree (SRT) that continuously encapsulates such redundancy at the service side and transforms trace spans into a lightweight form. At the backend, the complete traces can be seamlessly reconstructed by retrieving the common data that are already delivered by previous spans. Tracezip includes a series of strategies to optimize the structure of SRT and a differential update mechanism to efficiently synchronize SRT between services and the backend. Our evaluation on microservices benchmarks, popular cloud service systems, and production trace data demonstrates that Tracezip can achieve substantial performance gains in trace collection with negligible overhead. We have implemented Tracezip inside the OpenTelemetry Collector, making it compatible with existing tracing APIs.
