# Raft@ATC2014

> In Search of an Understandable Consensus Algorithm. ATC, 2014.

## Problem
Paxos is difficult to understand. Design an understandable one!
 
## Contribution
A new consensus protocol called Raft.
It is ultimate goal in correctness is the `State Machine Safety Property`:
> If a server has applied a log entry at a given index to its state machine, no other server will ever apply a different log entry for the same index.

Raft is decomposed into three key compoments:
- Leader election
	- `Election Safety Property`: at most one leader in a term
		- Method: majority-vote
		- `Leader Completeness Property`: 
		  - Method: the `RequestVote` from candidates with relatively stale log will be denied
- Replication
	- `Leader Append-Only Property`
	- `Log Matching Property`
		- Method: `AppendEntries` consistency check
- Safety (Commitment)
	- Never commits log entries from *pevious terms* of counting replicas.
	- Only log entries from the leader's *current term* are comitted by counting replicas; once an entry from the current term has been committed in this way, then all prior entries are committed indirectly because of the `Log Matching Property`

## Notes
About the `Log Matching Property`:
> If two logs contain an entry with the same index and term, then the logs are identical in all entries up through the given index.

For a given index, the entries across logs with the same index will be eventually the same, namely, having the same term and command. However, in the intermediate states of Raft, the entries with the same index may have different terms. 

## Ideas
- Byzantine Raft
- High-level Raft: 
	- To prove `State Machine Safety Property` from the other four properties: `Election Safety`, `Leader Completeness`, `Leader Append-Only`, `Log Matching`?
	- Need other properties? (Commitment restriction???)
- Industrial Implementations
	- PolarFS
	- Baidu Raft?
	- ???

> Written with [StackEdit](https://stackedit.io/).
