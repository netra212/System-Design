## Reliability
> Availability asks "Is the system up?"; reliability asks "Is the system doing what it should?"
> Reliability is the probability that a system will perform its intended function correctly over a given period of time, under specified conditions.
> This definition has several important parts.

* "Correctly" means producing the right output, not just any output.
* "Over a given period" means reliability is measured over time, not at a single instant.
* "Under specified conditions" means we define what normal operation looks like.

## Measuring Reliability
### 1.  Mean Time Between Failures (MTBF)
> MTBF measures the average time between failures. A higher MTBF means failures are less frequent.
> MTBF = Total Operating Time / Number of Failures

### 2. Mean Time To Recovery (MTTR)
> MTTR measures how long it takes to restore the system after a failure. A lower MTTR means faster recovery.
> MTTR = Total Downtime / Number of Failures

### 3. Error Rate
> Percentage of requests that result in errors.
> Error Rate = Failed Requests / Total Requests × 100%

### 4. Data Correctness
> Percentage of responses that contain correct data.

> Correctness = Correct Responses / Total Responses × 100%

> This is the often-overlooked metric. A system can have 99.99% availability and 0.01% error rate, but if 1% of successful responses contain wrong data, you have a reliability problem. Users received a response, it just was not the right one.

## Why Systems Become Unreliable
> 

## Key Principles of Reliable Systems
### 1. Redundancy
### 2. Failover Mechanisms
### 3. Load Balancing. 
### 4. Monitoring and Alerting
### 5. Graceful Degradation


## Techniques to Enhance Reliability
### 1. Redundant Architectures
### 2. Data Replication
### 3. Graceful Degradation
### 4. Circuit Breakers
### 5. Idempotency


## Summary
> Reliability is the probability that a system performs its intended function correctly over time. Availability asks if the system responds; reliability asks if the response is right.

> Key takeaways:

> Reliability, availability, fault tolerance, and durability are distinct properties. A system can be available and unreliable, or fault-tolerant but not durable. Optimizing for one can quietly sacrifice another.
> MTBF measures how often things break, MTTR measures how fast you recover. Reducing MTTR often has more impact than trying to prevent every failure.
> Error rate and correctness are both required. A response that never errors but contains wrong data still fails the user.
> Failures come from many sources. Hardware wear, software bugs, configuration mistakes, human error, and overload cascades each call for different defenses.
> Redundancy plus failover keeps the system serving when components die. An untested failover path is a false sense of safety.
> Graceful degradation reduces blast radius. Core flows should keep working when optional services fail; emergency mode is better than a blank page.
> Circuit breakers prevent one slow dependency from taking down the rest of the system. Fail fast, then recover deliberately.
> Idempotency makes retries safe. Money-moving operations should require an idempotency key so duplicate requests do not cause duplicate effects.
