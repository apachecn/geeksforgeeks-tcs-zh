# 证明循环群的每个子群都是循环的

> 原文:[https://www . geeksforgeeks . org/prove-循环群的每个子群都是循环的/](https://www.geeksforgeeks.org/prove-that-every-subgroup-of-a-cyclic-group-is-cyclic/)

**证明:**
循环群的每个子群都是循环的。

**循环群:**
它是由单个元素生成的群，该元素被称为该循环群的生成元，或者循环群 G 是群中每个元素都是特定元素 G 的幂的群。也就是说，对于乘法群的某个整数 n，G 的每个元素都可以写成 g <sup>n</sup> ，对于加法群的某个整数 n，可以写成 ng。所以，g 是 g 群的发生器。

**证明:**
我们假设 G 是由 a 即 G = {a}生成的循环群。
如果另一组 H 等于 G 或 H = {a}，那么显然 H 是循环的。
所以设 H 是 g 的适当子群，所以 H 的元素是 a 的整幂，如果 a <sup>s</sup> ∈ H，那么 a <sup>s</sup> 的逆，即；

```
a-s ∈ H
```

因此，H 包含正的和负的积分幂的元素。现在，让 m 是最小正整数，这样

```
am ∈ H
```

那么我们将证明:

```
H = { am }
```

即，H 是循环的并且由 <sup>m</sup> 生成。
设 a <sup>t</sup> 为 h 的任意元素
通过除法算法，存在整数 q 和 r，这样:

```
t = mq + r,    0 ≤ r <m.
```

现在，

```
  am ∈ H 
⇢(am)q ∈ H 
⇢ amq ∈ H
⇢(amq)-1 ∈ H
⇢a-mq  ∈ H.
```

还有，

```
at  ∈ H
a-mq  ∈ H ⇢ at a-mq  ∈ H
⇢ at-mq  ∈ H
⇢ ar  ∈ H.      (Since, r = t- mq)
```

现在 m 是最小正整数，这样:

```
am ∈ H,      0 ≤ r <m.
```

因此，r 必须等于 0。
因此，

```
 t = mq                    
```

因此，

```
at = amq =(am)q .
```

因此，每个元素 a <sup>t</sup> ∈ H 的形式是(a <sup>m</sup> ) <sup>q</sup> 。
因此，H 是循环的，并且 <sup>m</sup> 是 H 的生成。因此，证明了循环群(G)的每个子群(在这种情况下是 H)是循环的。