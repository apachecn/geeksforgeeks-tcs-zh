# 举例理解马尔可夫定理

> 原文:[https://www . geeksforgeeks . org/understance-Markov-定理-举例说明/](https://www.geeksforgeeks.org/understanding-markovs-theorem-with-example/)

在本文中，我们将讨论马尔可夫定理的概述，也将讨论马尔可夫定理的表达，最后用一个例子来理解马尔可夫定理。我们一个一个来讨论。

**马尔可夫定理** :
马尔可夫定理指出，如果 R 是非负的(意味着大于或等于 0)随机变量，那么，对于每个正整数 x，该随机变量 R 大于或等于该正整数 x 的概率是 x 上随机变量 R 的期望值的上限

**马尔可夫定理的表达:**
数学上可以写成如下。

```
If R >=0 , then ∀ x >0,
P(R>=x) <= Ex( R ) / x
```

**需要记住的要点:**
请注意，应用上述马尔可夫定理，随机变量 R 必须是非负的。

```
If R is non-negative ∀ C > 0, then
P (R >= c*Ex( R ) ) <= 1/c 
```

马尔可夫定理的扩展版本陈述如下表达式。

```
If R ≤ U for some U in the set of a real number ( U ∈ IR) then,
∀ x >0,
P(R ≤ x) ≤ (U - Ex( R ) ) / ( U- x )
```

**例子:**
这里，我们将讨论理解这个马尔可夫定理的例子如下。
假设在一个 100 分的班级测试中，学生的平均分数是 75 分。那么随机从班上选出来的学生小于 0r 等于 50 分的概率是多少。

为了解决这个问题，让我们定义一个随机变量 R =随机学生的分数。由于 R 的上界是 100，所以我们使用上面讨论的马尔可夫定理的扩展版本。

现在，通过使用下面给出的马尔可夫定理的表达式，我们将如下解决这个问题。

```
Expression :
If R >=0 , then ∀ x >0,
P(R>=x) <= Ex( R ) / x 
```

```
So, U = 100,
Ex ( R ) = 75
then, use the above formulae,
P (R <= 50 ) = (  100-  75) / ( 100- 50  ) = 25/ 50 = 1/2
which gives the answer as 0.5 
```

所以，随机学生的分数几乎是 50 的概率上限是 0.5