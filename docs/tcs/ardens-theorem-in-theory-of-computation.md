# 计算理论中的阿登定理

> 原文:[https://www . geeksforgeeks . org/ardens-计算理论定理/](https://www.geeksforgeeks.org/ardens-theorem-in-theory-of-computation/)

**阿登定理**陈述:
“如果 P 和 Q 是![ $\sum_](img/ca4556ee856e052932618813168353f2.png "Rendered by QuickLaTeX.com")上的两个正则表达式，并且如果 P 不包含![ $\epsilon_](img/7a7720d68d11892c0496bba552ab3d85.png "Rendered by QuickLaTeX.com")，那么 R = Q + RP 给出的 R 中的下式有唯一解，即 R = QP*。”
也就是说，每当我们得到任何一个 R = Q + RP 形式的方程，那么我们就可以直接用 R = QP*来代替。所以，这里我们首先证明 R = QP*是这个方程的解，然后我们也证明它是这个方程的唯一解。

让我们从这个方程作为方程(I)开始

```
R = Q + RP  ......(i)
```

现在，用 R = QP*代替 R，我们得到，

```
R = Q + QP*P 
```

以 Q 为常见，

```
R = Q( + P*P)
R = QP*  
```

(我们知道![ $\epsilon_](img/7a7720d68d11892c0496bba552ab3d85.png "Rendered by QuickLaTeX.com") + R*R = R*)。因此被证明。

*因此，R = QP*是方程 R = Q + RP 的解。*

现在，我们必须证明这是这个方程的唯一解。让我再来看看这个等式:

```
R = Q + RP
```

现在，用 R = Q + RP 代替 R，

```
R = Q + (Q + RP)P
  = Q + QP + R 
```

同样，用 R = Q + RP 替换 R:-

```
R = Q + QP + (Q + RP) 
  = Q + QP + Q + R
  = ...
  = ...
  =  Q + QP + Q + .. + Q + R 
```

现在，用 R = QP*代替 R，我们得到，

```
R = Q + QP + Q + .. + Q + QP* 
```

以 Q 为常见，

```
R = Q( + P +  + .. +  + P*)
  = QP*    [As  + P +  + .. +  + P* represent 
          the closure of P] 
```

因此被证明。

**因此，R = QP*是方程 R = Q + RP 的唯一解。**

为了理解这个定理，我们将求解一个例子:

**示例–**

```
q1 = q1.0  + 
q2 = q1.1 + q2.0
q3 = q2.1 + q3.0 + q3.1 
```

现在，

```
q1 =  + q1.0
q1 = .0*    [By Arden's theorem]
q1 = 0*      [R = R]

.'. q2 = 0*1 +q2.0
    q2 = 0*10*    
```

【应用阿登定理】。因此，q2 的值是 0*10*。