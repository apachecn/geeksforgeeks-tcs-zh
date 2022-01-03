# 证明有限群的元素是有限的

> 原文:[https://www . geesforgeks . org/proof-elements-of-a-limited-group-is-limited/](https://www.geeksforgeeks.org/proving-elements-of-a-finite-group-is-finite/)

**证明** :
有限群的每个元素的阶都是有限的，并且小于或等于群的阶。

**证明** :
假设 G 是一个有限群，其组成是乘法表示的。假设 a ∈ G，考虑 a 的所有正整数幂，即 a，a <sup>2</sup> ，a <sup>3</sup> ，……
所有这些都是 G 的元素，通过闭包公理。
由于 G 的元素数量有限，因此 **a** 的所有这些积分幂都不能是 G 的不同元素

假设，

```
ar = as    where r > s
```

现在

```
ar = as 
=> ar . a-s = as . a-s      (multiplying both sides by a-s )
=> ar . a-s = a0            ( as-s = a0)
=> ar . a-s = e 
=> am = e,                 where m = r - s 
```

因为

```
r > s
```

因此，“m”是正整数。因此，存在正整数 m，使得 a <sup>m</sup> = e。

现在我们知道每组正整数都有最少的成员。
因此，所有那些正整数 m 的集合使得 a <sup>m</sup> = e 具有最少的成员，比如 n。因此，存在最少的正整数 n，使得

```
an = e. 
```

因此，a，o(a)的阶是有限的。
现在来证明 o(a) ≤ o(G)。

假设，

```
o(a) = n, where n > o(G). 
```

既然 a ∈ G，那么由闭包属性 a，a <sup>2</sup> ，…。a <sup>n</sup> 是 g 的元素，没有两个是相等的。如果可能的话，让 a <sup>r</sup> = a <sup>s</sup> ，1 ≤ s < r ≤ n .然后，

```
ar-s = e
```

因为

```
0 < r - s < n
```

因此，

```
ar-s = e implies that the order of a is less than n. 
```

这是一个矛盾。因此，a，a <sup>2</sup> ，… a <sup>n</sup> 是 G 的 n 个不同元素。由于 n > o(G)，因此这是不可能的。
因此，我们必须有 o(a) ≤ o(G)。

因此，证明了有限群(G)的每个元素(a，o(a))的阶都是有限的，且小于或等于群的阶(即 o(a) ≤ o(g))。