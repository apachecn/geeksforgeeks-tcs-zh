# 用证明和例子理解墨菲定律

> 原文:[https://www . geesforgeks . org/understanding-murphys-law-with-proof-and-examples/](https://www.geeksforgeeks.org/understanding-murphys-law-with-proofs-and-examples/)

在这篇文章中，我们将讨论外行术语墨菲定律的概述，然后我们将主要关注证明和解释，并将通过证明和例子来理解墨菲定律。我们一个一个来讨论。

**概述:**
用外行人的话来说，墨菲定律说的是“如果某件事会出错，它就会出错”。数学上，给定相互独立的事件 A1，A2，…安。

```
And T = number of events to occur,
Ex( T ) denotes the expected number of events to occur.
```

那么墨菲定律说，没有一个独立事件会发生的概率是这个表达式的上限，如下所示。

```
e^( -Ex(T)).  
```

或者

```
P( T =0 ) ≤ e ∧-Ex(T)                                         
```

**证明:**【2】证明中，Ai 处处表示 i= 1，2…n。

```
[Tex]P(A1' ∩ A2' ∩ ......An')[/Tex]
```

```
       = ∏ (P(Ai') ) for i= 1,2....n
```

```
       =  ∏ (1-P(Ai))                     step 3 
       ≤  ∏ (e^-P(Ai))                    step 4
       ≤  e ^[∑ (-P(Ai))]                 step 5
       ≤ e ^ -Ex(T)                       step 6
```

**证明解释:**
为了理解第 3 步到第 4 步，阅读一点关于泰勒级数的内容，对 e^-x 使用泰勒级数，并使用如下近似。

```
  e^-x ≥ 1-x 
= 1-x ≤ e^-x , In our case, x is equivalent to P(Ai)
```

**了解第 4 步至第 5 步–**

```
  ∏ (e^-P(Ai))   
= e^-P(A1) * e^-P(A2) * e^-P(A3) ....... e^-P(An)
= e^-{A1+A2+A3 +.....+An}
= e ^[∑ (-P(Ai))]
```

**要理解第 5 步到第 6 步–**
回想一下预期发生的事件数量的定义，如下所示。

```
= Ex(T) = ∑ (P(Ai)) for i= 1 to n.
```

于是，证明了。给定概率空间 S 和事件 A1，A2……。安。都在 s .那么下面的表达式如下。

```
Expected number of events to occur = Ex(T) = ∑ P(Ai) for i = 1...n
```

既然我们已经证明了墨菲定律。

**例-1 :**
我们来看一个例子来理解这个。假设有一千个事件要对一个核反应堆的故障负责，发生的事件数的期望值是 10。假设所有事件都是相互独立的。那么这些因素都不会发生，从而不会失败的概率是多少？

**解决方案–**
从问题中，我们知道 Ex(T) =10，其中 T =导致失败的预期事件数。根据墨菲定律，所有事件都不会发生的概率以 e <sup>-10</sup> 为上限，即 0.000045。所以，至少有一个事件导致失败的几率是= 1- e <sup>-10</sup> = 0.999955。这就是墨菲定律的影响，对于计算机专业的学生来说，这是数学中非常重要的概念。

**参考文献:**
https://en.wikipedia.org/wiki/Taylor_series