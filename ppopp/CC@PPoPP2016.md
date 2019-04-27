# CC@PPoPP'2016

Causal Consistency: Beyond Memory

## Section 6: Implementation in Wait-free Systems
wait-free 是否是必须的?

如果 failure model 放松为 majority, 能否带来其它方面的好处?

### Section 6.2: Implementation of Causal Consistency
在设计分布式协议实现某种一致性模型时, 实现得弱了, 自然是错误的, 实现得强了, 可能也是有问题的。比如, 使用了过强的通信原语。
