# DEC@PhD Thesis'2015

> ***Dependable Eventual Consistency with Replicated Data Types, Marek Zawirski, PhD Thesis, 2015.*** 

## Chapter 6
> Goal: Causally-Consistent Object Database for Client-Side Applications

重点在于: Client-Side

### 6.1 System Model
App + Client + DC

### 6.2 Consistency
#### 6.2.1 Causal Consistency
- 在 Def 6.1 中, 标注了 "one per ***application process*** session"
- 这是 PoEC@NOW'2014 与 RDT@POPL'2014 中定义的带 convergence 的 Causal Consistency
- 与四种 Session Gurantees 等价 (Section 9.2.1.3)
- 在提到 causal transaction 时, 使用了 "A transaction is a sequence of operations issued by a single ***client*** session."

#### 6.2.2 Convergence
- Convergence = Eventual Visibility (liveness) + Confluence (safety)
- Op-based RDT over causal delivery

### 6.3 Application Programming Interface
- begin_tx
- read
- update
- commit_tx

### 6.4 Challenge
#### 6.4.1 Metadata Design
- Client-Assigned, Safe but Fat
- Server-Assigned, Lean but Unsafe

#### 6.4.2 Partial Replication



> Written with [StackEdit](https://stackedit.io/).
