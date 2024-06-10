Source:
https://www.youtube.com/watch?v=sGzQT_ZrsFI&ab_channel=ScientificProgrammingSchool

Books:
Kleppmann Designing data-intensive applications

Concurrent systems - Distributed systems

Why Distributed systems?
- inherited
- reliable
- better performance (get optimization)
- to solve bigger problems

Disadvantages:
- communications may fail
- processes may crash

Data intensive - big amount of the data is main problem (unlike compute-intensive where CPU is a bottleneck).

- Reliability - a system should work correctly even in unfavorable circumstances (HW or SW failures, or user mistakes)
- Scalability - there should be solutions to solve grows problems (increase amount of data, traffic or system complexity)
- Maintainability

## Reliability

Fault - about one component of the system. Failure - of whole system.
Chaos Monkey of the Netflix - random faults for testing
(mean time to failure, MTTF)
- HW errors
- SW errors
- Human errors


## Scalability
Load description - load parameters:
- requests per second to a web server 
- ratio of reads to writes in a database
- number of simultaneously active users in a chat room, 
- hit rate on a cache

```
Latency and response time are often used synonymously, but they
are not the same. The response time is what the client sees: besides
the actual time to process the request (the service time), it includes
network delays and queueing delays. Latency is the duration that a
request is waiting to be handled—during which it is latent, await‐
ing service
```

It's better to use median (p50, 50th percentile) for the response time rather than avg.

**Tail latencies** - high percentiles of response time (p99, p999)

## Maintainability
Design principles:
- Operability - make it easy for operations teams to keep the system running smoothly
- Simplicity - Make it easy for new engineers to understand the system, by removing as much
complexity as possible from the system.
- Evolvability - Make it easy for engineers to make changes to the system in the future, adapting
it for unanticipated use cases as requirements change. Also known as *extensibility*, *modifiability*, or *plasticity*.

