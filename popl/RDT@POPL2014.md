# RDT@POPL'2014

> **Replicated Data Types: Specification, Verification, Optimality**

## Section 5: Proving Data Type Implementations Correct

5.2 节定义的 abstract methods $\text{do}^{\sharp}$, $\text{send}^{\sharp}$ 与 $\text{receive}^{\sharp}$ 为 state-based CRDT 提供了操作语义。

附录 B (Fig. 18) 中定义的 abstract methods 为 op-based CRDT 提供了操作语义。

***$Q:$*** 将 transport layer 抽象出来, 得到一个更 high-level 的、适用于 state-based 与 op-based CRDT 的操作语义?
