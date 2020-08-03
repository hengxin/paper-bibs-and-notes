# RedBlue@OSDI2012

> Making Geo-Replicated Systems Fast as Possible,
Consistent when Necessary. OSDI, 2012.

## Problem
- Fast vs. Consistent tradeoff

Solution: Fast as possible, Consistent when necessary

## Contribution

### RedBlue Consistency
> RedBlue consistency is based on an explicit division
of operations into blue operations whose order of
execution can vary from *site to site*, and red operations
that must be executed in the same order *at all sites*.

Question: Replica/Site-view vs. Client-view?

Note: RedBlue Order is defined as a partial order over all operations instead of a total order over all Red operations.
This is helpful to define `causal serialization` (below) as an extension of the RedBlue Order.

> Definition (RedBlue Order): A partial order over all operations (either Red or Blue) in which all Red operations are totally ordered.

RedBlue Order is global for all sites.
> Definition (Causal Serialization): A linear extension of the RedBlue order such that ...

Question: What does "Condition (2) of Definition 2" mean?

### State Convergence
> A *RedBlue consistent system* is state convergent if *all* causal serializations of the underlying RedBlue order O reach the same state S.

> **Theorem 1**. Given a RedBlue order O, if all blue operations are *globally commutative*, then any O-RedBlue
consistent system is state convergent.

Thus, we need to increase commutativity.

### $u = g_{u} + h_{u}(S)$
- The *generator operation* decides which state transitions should be made while the *shadow operation* applies the transitions in a *state-independent* manner.

## Implementation
A site consists of
- a storage engine
- a proxy server
- a concurrency coordinator
> To admit or reject a shadow operation according to RedBlue consistency
- a data writer

Each site maintains a vector clock with $n + 1$ entries, where the $(n+1)$-st entry $r$ is the *global* count of red shadow operations.

To ensure the uniqueness of $r$, the protocol uses the red-token-passing mechanism among concurrency coordinators.

The other parts of the protocol is similar to standard causal consistency protocols.

## Ideas
- The RedBlue Consistency protocol is not fault-tolerant, especially because of the token-passing mechanism for ordering red operations.

> Written with [StackEdit](https://stackedit.io/).
