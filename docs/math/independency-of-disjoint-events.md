# 不相交事件的独立性

> 原文:[https://www . geeksforgeeks . org/independency-of-exclusive-events/](https://www.geeksforgeeks.org/independency-of-disjoint-events/)

当我们同时掷两枚公平的硬币时。直觉上，一枚硬币落地的方式不会影响另一枚硬币落地的方式。抓住这一点的数学概念叫做独立性。

**独立事件的定义:**
事件 A 和 B 是独立的，如果–

```
 1\. P(B)=0 or
 2\. P(A | B) = P(A)
```

换句话说，如果知道 B 发生不会改变 A 发生的概率，A 和 B 是独立的，就像抛两个硬币一样。
有时候我们会得到不相交的事件是独立的这种想法，但事实上，恰恰相反。

**不相交的事件不是独立的。**

**证明:**
如果两个事件不相交，那么我们知道，a∪b =∅；这意味着知道 A 发生意味着你知道 B 没有发生。
现在假设，

```
P(B) != 0 .
P(A | B) = P( A ∩ B ) / P( B )
```

因为事件是分离的:

```
P( A ∩ B ) = 0
P(A | B) = 0 , which is not equal to P( A ).
```

因此，独立事件的数学定义失败，从而证明**不相交事件不是独立事件。**