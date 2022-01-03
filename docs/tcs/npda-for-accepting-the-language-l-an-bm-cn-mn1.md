# NPDA 接受语言 L = {an bm cn | m，n > =1}

> 原文:[https://www . geesforgeks . org/npda-for-accepting-language-l-an-BM-cn-mn1/](https://www.geeksforgeeks.org/npda-for-accepting-the-language-l-an-bm-cn-mn1/)

先决条件–[下推自动机](https://www.geeksforgeeks.org/theory-of-computation-pushdown-automata/)、[下推自动机按最终状态接受](https://www.geeksforgeeks.org/pushdown-automata-acceptance-final-state/)
**问题–**–设计一个非确定性的 PDA 接受语言 L = { ![a^n](img/347b4ff81cbcc2fb2ff95c05c9438df8.png "Rendered by QuickLaTeX.com") ![b^m](img/c1cbbd3e7feed0b5ce034d037ac3042a.png "Rendered by QuickLaTeX.com") ![c^n](img/97b250e692e3e7724459e6cb9391247e.png "Rendered by QuickLaTeX.com") | m，n > =1}，即，

```
 L = { abc, abbc, abbbc,  aabbcc, aaabccc, aaaabbbcccc, ...... } 
```

在每个字符串中，a 的数目等于 c 的数目。b 的数量与 a 和 c 的数量无关。这个问题相当类似于 NPDA 对于语言的接受 L = { ![a^n](img/347b4ff81cbcc2fb2ff95c05c9438df8.png "Rendered by QuickLaTeX.com") ![b^n](img/ccc205985e45e55e57f89bc858ee68c9.png "Rendered by QuickLaTeX.com") ![c^m](img/464fc0e56bed6af5a568e96272c895d5.png "Rendered by QuickLaTeX.com") | m，n > =1}。唯一不同的是，这里我们用![b^m](img/c1cbbd3e7feed0b5ce034d037ac3042a.png "Rendered by QuickLaTeX.com")代替![c^m](img/464fc0e56bed6af5a568e96272c895d5.png "Rendered by QuickLaTeX.com")。

**解释–**
在这里，我们需要维持 a、b、c 的顺序，也就是所有的 a 都是先来，然后所有的 b 然后 c 都来。因此，我们需要一个堆栈和状态图。a 和 c 的计数由堆栈维护。a 的数量正好等于 c 的数量我们将取 2 个堆叠字母:

```
 = { a, z }

```

其中，![\Gamma](img/7227a362929bad8def3d7ea099742850.png "Rendered by QuickLaTeX.com") =所有堆栈字母表的集合
z =堆栈开始符号

**PDA 建设中采用的手法–**
由于我们要设计一个 NPDA，因此每次‘a’都排在‘b’之前。当“a”出现时，将它推入堆栈，如果“a”再次出现，也将它推入堆栈。当 c 出现时，每次从堆栈中弹出一个 a。而对于‘b’，我们在栈中什么也不做，只改变状态图中的状态。
所以，最后如果堆栈变空，那么我们可以说字符串被 PDA 接受了。

**堆栈转换功能–**

```
(q0, a, z)  (q0, az)
(q0, a, a)  (q0, aa)
(q0, b, a)  (q1, a)
(q1, b, a)  (q1, a)
(q1, c, a)  (q2,  )
(q2, c, a)  (q2,  )
(q2, , z)  (qf, z )

```

其中，q0 =初始状态
qf =最终状态
![\epsilon](img/9e0d0faaeb36399f71c3ccdd6c2b69d0.png "Rendered by QuickLaTeX.com") =表示弹出操作

![](img/83184e84826a94e5cbe0193cb49af2dd.png)

所以，这就是我们所要求的非确定性 PDA 对于接受语言 L = { ![a^n](img/347b4ff81cbcc2fb2ff95c05c9438df8.png "Rendered by QuickLaTeX.com") ![b^m](img/c1cbbd3e7feed0b5ce034d037ac3042a.png "Rendered by QuickLaTeX.com") ![c^n](img/97b250e692e3e7724459e6cb9391247e.png "Rendered by QuickLaTeX.com") | m，n > =1 }。