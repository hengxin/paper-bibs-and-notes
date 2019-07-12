# CC@PPoPP'2016

> ***Causal Consistency: Beyond Memory, PPoPP, 2016.***

## Specifications
### $CC_v:$ Causal Convergence
- $ar_g$ 是 "all updates":
	- Section 5.1 的文字描述是: "in causal convergence, the *updates* are totally ordered and the state read by each operation is the result of the *updates* in its causal past, ordered by this common total order."
	- Definition 12 中在 $\le$ 中没有明确说明是 "all updates"。但是由于 $CC_v$ 中 hide 所有的读操作, 所以实际效果等同于 $\le$ 限制在了 "all updates" 上。
- 

## Section 6: Implementation in Wait-free Systems
wait-free 是否是必须的?

如果 failure model 放松为 majority, 能否带来其它方面的好处?

***Quorum + Reliable Causal Broadcast = ?*** (参考 causal convergence 文章)

What about *causal+ consistency*?

### Section 6.2: Implementation of Causal Consistency
在设计分布式协议实现某种一致性模型时, 实现得弱了, 自然是错误的, 实现得强了, 可能也是有问题的。比如, 使用了过强的通信原语。



## Research Ideas
- 实现 Variants of Causal Consistency:
  - [ ] 共有的部分: causal broadcast (vector clock)
	- [ ] *能否弱化?*
  - [ ] WCC: +logical clock (aka, Lamport clock)
  - [ ] CC: +nothing
  - [ ] CCv: +(logical clock, pid)

- What about *version clock*?

- 关于 Convergence:
  - [ ] EC, SEC, UC 之间是什么关系?

- Causal Consistency 变体验证
  - [ ] TLA vs. Coq
  - [ ] Client Program + Protocol

## TODO

