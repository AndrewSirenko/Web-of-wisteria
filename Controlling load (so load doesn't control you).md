TODO Traffic Jam Example

See [[Throttling + Rate Limit Tips]], [[No Compression Algorithm for Experience]]

Load stresses systems. Stressed systems perform worse.[^1] Therefore, a system can get so loaded that it stops working at all. If we don't want our systems to jam up when we need them most, we need to design them to proactively manage load.

1. Find the inflection point
	1. Every system has an inflection point for latency vs throughput, and a total brownout after that (And if you think your system is the exception, you just haven't found it yet...)
	2. Load test! Graph Goodput (Served transactions per second (TPS) vs Incoming TPS)
3. Throttle
	1. Cheaply reject excess work
	2. Throttling keeps a system alive for the scale it was built for. 
4. Know what you're throttling
	4. Prioritize the ambulances
	5. Prioritize health checks (don't lose capacity when it's already raining)
	6. Cap noisy neighbors first
	7. Throttling should be 'fair' in a multi-tenant system.  (Advanced: [Fairness in multi-tenant systems](https://aws.amazon.com/builders-library/fairness-in-multi-tenant-systems/?did=ba_card&trk=ba_card))
5. Shed load as far forward as you can
	1. If we're getting behind, reject load proactively as to not get more behind
	3. Turn away folks before they get into a traffic jam
	4. [Load Shedding Strategy](https://aws.amazon.com/builders-library/using-load-shedding-to-avoid-overload/)
6. Stop working if nobody is listening
	1. Don't be oblivious to the timeouts of your callers
	2. Add Time to Lives (TTL)
7. Be wary of queues (and congestive collapse)
	1. A backlog can grow forever
	2. Bound the queue, measure dwell time, consider a PQ
	5. Consider LIFO instead of FIFO (life is unfair, but it maximizes non garbage work)
	6. [Queue Backlog Avoidance](https://aws.amazon.com/builders-library/avoiding-insurmountable-queue-backlogs/?did=ba_card&trk=ba_card)
8. Avoid fallback
	1. Don't do more work when things go wrong
	2. [Avoiding Fallback](https://aws.amazon.com/builders-library/avoiding-fallback-in-distributed-systems/)
9. Put the smaller system in control 
	1. [Avoiding Overload Control](https://aws.amazon.com/builders-library/avoiding-overload-in-distributed-systems-by-putting-the-smaller-service-in-control/?did=ba_card&trk=ba_card)
10. Let clients retry (correctly)
	1. [Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/?did=ba_card&trk=ba_card)
	2. [Timeouts, retries and backoff with jitter](https://aws.amazon.com/builders-library/timeouts-retries-and-backoff-with-jitter/?did=ba_card&trk=ba_card)
	3. Consider having the latency of rejections the same as average successful latency to make sure rejects don't take up more work. 

## Notes

[^1]: Unless you've designed an *anti-fragile* system which becomes more efficient under peak stress. Check out [Work Ethic and Coffee |  Amazon Builders' Library](https://aws.amazon.com/builders-library/reliability-and-constant-work/?did=ba_card&trk=ba_card)

