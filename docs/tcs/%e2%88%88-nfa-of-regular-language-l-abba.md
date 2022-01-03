# ∑-常规语言的 L = { ab，ba}

> 原文:[https://www . geesforgeks . org/% E2 % 88% 88-NFA-of-regular-l-ABBA/](https://www.geeksforgeeks.org/%e2%88%88-nfa-of-regular-language-l-abba/)

**先决条件–**[有限自动机介绍](https://www.geeksforgeeks.org/introduction-of-finite-automata/)

非确定性有限自动机和[∑-非确定性有限自动机](https://www.geeksforgeeks.org/conversion-of-epsilon-nfa-to-nfa/)除了它们的转移函数和构造∑-NFA 的一些特殊规则外，几乎是一样的。

```
∈-NFA is defined in 5 tuple representation {Q, q0, Σ, δ, F} where,
Q is the set of all states,
q0 is the initial state,
Σ is the set of input symbols,
δ is the transition function which is δ:Q × (Σ∪∈)->2Q and
F is the set of final states.

```

**构造∑-NFA 的简单规则:**

```
∈-NFA for a+ :
```

[![](img/541b1add37a627710ba93e9576bb20e0.png)](https://media.geeksforgeeks.org/wp-content/uploads/20201004223230/NFAofa.jpg)

这个结构是针对一个 <sup>+</sup> 的，也就是说表达式中至少要有一个“a”。它的前面是ε，后面也是 1。从状态 q <sub>2</sub> 到 q <sub>1</sub> 有ε反馈，所以表达式中可以有多个 a”。

```
∈-NFA for a* :
```

[![](img/6813a46362220fb8c0a628a9e053e058.png)](https://media.geeksforgeeks.org/wp-content/uploads/20201004223748/NFAofaclosure.jpg)

这个结构是 a*的，这意味着表达式中可以有任意数量的“a”，甚至是 0。前面的结构只是修改了一点，这样即使没有输入符号，即如果输入符号为空，那么表达式也是有效的。

```
∈-NFA for a+b :
```

[![](img/432cb3aa5fbc59533d6136f8eb054575.png)](https://media.geeksforgeeks.org/wp-content/uploads/20201004232537/NFAofab.jpg)

该结构接受 a 或 b 作为输入。所以有两条路，都通向最终状态。

```
∈-NFA for ab :
```

[![](img/4fc6af2458a6540192ba4e247ec3d92f.png)](https://media.geeksforgeeks.org/wp-content/uploads/20201004232659/NFAofab.jpg)

对于串联，a 后面必须跟 b，只有这样才能达到最终状态。这里允许两种结构，但是因为它是∑-NFA，所以推荐第二种结构。

**∑-NFA 为 L = {ab，ba} :**
遵循上述规则，构造正则语言 L ={ab，ba}的∑-NFA。

语言由 ab 或 ba 组成，也可以写成(ab + ba)。遵循构造加法或(a+b)的规则，我们必须构造主结构。然而，在这里，a+b 中的“a”实际上是表达“ab”，a+b 中的“b”实际上是表达“ba”。所以，我们只是替换它们的结构，分别代替 a 和 b。所以最终∑-NFA 会有两条路，一条是 ab 路，另一条是 ba 路，这两条路都通向最终状态。

遵循构造连接或 ab 的规则，我们可以分别构造 ab 和 ba 的结构。对于级联，可以选择上述两种结构中的任何一种，即有或没有ε，但是我们选择有ε的结构，因为它是∑-NFA。

**决赛∑-NFA 将是:**

[![](img/a544d400e1c11947e2d8c4c0d1a7d45e.png)](https://media.geeksforgeeks.org/wp-content/uploads/20201004233953/NFAofLabba.jpg)