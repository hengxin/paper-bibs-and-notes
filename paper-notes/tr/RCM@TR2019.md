# RCM@TR2019

> Resilient Causal Memory in Client-Server Model. TR, 2019.

## Assumptions
- Full Replication
- Static System

## Supported
- Client migration???

## Properties
### Safety: Causal Consistency in the Presence of Faults
Defined on *complete* histories.

### Liveness: Availability
Every operation can be completed in finite amount of time given that the client does not crash and at most $f$ servers crashes.

> Avaialability does not exclude the trivial solution: returning initial value $\bot$ for each read and ignoring any write.

### Convergence
#### Persistence
#### Weak Convergence

## Protocols
### Dependency Tracking
Using vector clock of size $n_c$.
- Shortcoming: This is considered impractical.

### RCM
- CM + URB (Uniform Reliable Broadcast with Majority-ACK) + Stateless Clients
- Blocking
- Persistence + Weak Convergence

### Fast-RCM
- CM + URB + Stateful Clients
- Non-blocking
- Weak Convergence
- No Persistence guarantee

## Techniques to Learn
### Proof method for CM (A new way for constructing serialization)
- *In RCM, clients do not see all the writes.*
- Rule 2 for constructing valid serializations

## Ideas
- Supporting data partitions
- Using Server-side vector clocks to replace Client-side vector clocks
- Cure-based; Blocking vs. Non-blocking
- To support transactions
- ***Stateful + Non-blocking + Persistence + Weak Convergence***

> Written with [StackEdit](https://stackedit.io/).
