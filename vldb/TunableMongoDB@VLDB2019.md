# TunableMongoDB@VLDB2019

> Tunable Consistency in MongoDB. VLDB, 2019

## Summary
It describes
- Section 2: Tunable consistency in terms of `read-concern` and `write-concern` in MongoDB
- Section 3: Use cases
- Section 5: Multi-document transactions
	- Spectulative majority and snapshot isolation
- Section 6: Implementation
	- Speculative Execution Model
	- Data Rollback
- Section 8: Experiments
	- Latency vs. `write-concern`
	- `w:1` write loss in Fail-stop model
	- Failover

# Ideas
- TLA+ for Tunable Consistency Protocol in MongoDB 
- TLA+ for Data Rollbak
- TLA+ for multi-document transactions
- Some manual proofs
- TLAPS proofs
- Source code => TLA+???

> Written with [StackEdit](https://stackedit.io/).
