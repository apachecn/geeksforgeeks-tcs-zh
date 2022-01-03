# 队列自动机介绍

> 原文:[https://www . geesforgeks . org/introduction-to-queue-automator/](https://www.geeksforgeeks.org/introduction-to-queue-automata/)

我们已经知道[有限自动机](https://www.geeksforgeeks.org/introduction-of-pushdown-automata/)可以用来接受正则语言，[下推自动机](https://www.geeksforgeeks.org/introduction-of-pushdown-automata/)可以用来识别上下文无关语言。

队列自动机(QDA)是一种非确定性自动机，类似于下推自动机，但有一个队列而不是堆栈，这有助于队列自动机识别上下文无关语言之外的语言。

QDA 是一个 6 元组![M = (Q, \sigma, \Gamma, \delta, q_0, F)](img/0facb790dccf3c8fc7606c3a9264507d.png "Rendered by QuickLaTeX.com")

在哪里

1.  **Q** 是有限状态的集合。
2.  ![\bf{\sigma}](img/7c951f101cd0c72a3aa1288f89e9b0f2.png "Rendered by QuickLaTeX.com")是有限输入字母的集合。
3.  ![\bf{\Gamma}](img/9293ab627e8c261d98a692bc65e47415.png "Rendered by QuickLaTeX.com")是有限队列字母表的集合。
4.  ![\delta : Q \times \sigma_\epsilon \times \Gamma_\epsilon \rightarrow P(Q \times \Gamma_\epsilon )](img/c867109393f8d9cca932795d42405b15.png "Rendered by QuickLaTeX.com")。
5.  ![q_0 \in Q](img/44c246cef9e380e7a0696c359a369985.png "Rendered by QuickLaTeX.com")是开始状态。
6.  **F**T2【Q】是接受状态的集合。

**接受一根绳子**

如果![w](img/b27d57e3f417abb002a05eaa8a1ff42e.png "Rendered by QuickLaTeX.com")可以写成![w= w_1w_2w_3 ... . w_m](img/3b03510141b5821946ea0f74c4469ab4.png "Rendered by QuickLaTeX.com")，则 QDA ![M = (Q, \sigma, \Gamma, \delta, q_0, F)](img/0facb790dccf3c8fc7606c3a9264507d.png "Rendered by QuickLaTeX.com")接受输入![w](img/b27d57e3f417abb002a05eaa8a1ff42e.png "Rendered by QuickLaTeX.com")，其中每个![w_i \in](img/252a16295f5f6d07b4246be27edcbcd9.png "Rendered by QuickLaTeX.com") ![\sigma_\epsilon](img/7c31d672f502954a0faae0b5faf72307.png "Rendered by QuickLaTeX.com")都存在状态![r_0, r_1, r_2, ... . ., r_m \in Q](img/95b912d015afbd5ba9f7938345849985.png "Rendered by QuickLaTeX.com")和字符串![s_0, s_1, s_2, ... . ., s_m \in \Gamma^*](img/0c6e95ad6326c31d9a0a5b23e19ec9e4.png "Rendered by QuickLaTeX.com")，满足以下条件:

1.  ![r_0 = q_0](img/b2587cede6c99670327a990b1d0e8bb5.png "Rendered by QuickLaTeX.com")和![s_0 = \epsilon](img/e41b954e0c94cf8ef5e1ec22db9fc445.png "Rendered by QuickLaTeX.com")。
2.  对于![0\leq i \leq m-1](img/91c8a44d690447ec329943c46caa8c10.png "Rendered by QuickLaTeX.com")![( r_{i+1}, b) = \delta(r_i, w_{i+1}, a), where\, a, b \in \Gamma_\epsilon](img/27be81c60ff90a15b1d4c43176a7e20b.png "Rendered by QuickLaTeX.com")![s_i = ta](img/e9fbe4f4861688bc65f2eb82a6b06aa9.png "Rendered by QuickLaTeX.com")![s_{i+1} = bt](img/e920e243cfb192eb4092c1eb86c006e3.png "Rendered by QuickLaTeX.com")和![t \in \Gamma^*](img/dd0bf32dadacec389ac51af858a4c0a7.png "Rendered by QuickLaTeX.com")
3.  ![r_m \in F](img/52448f6594fdb933acc6fe6529a64b82.png "Rendered by QuickLaTeX.com")

**例:**
定义语言的队列自动机![{a^nb^n | n \geq 0}](img/fe241c94df667d8b4cb6d091cb2dd665.png "Rendered by QuickLaTeX.com")

**解:**
Q = {q0，q1，q2，q3}和![\sigma](img/27c8e782b604250720b0fdd48f6135e5.png "Rendered by QuickLaTeX.com") ={a，b}和![\Gamma](img/7227a362929bad8def3d7ea099742850.png "Rendered by QuickLaTeX.com") = {a，b，$}
而过渡函数由:
![\delta(q0, a, \epsilon)={(q0, a)}](img/5cc5060ae5c09ed2c4dbb040baad8511.png "Rendered by QuickLaTeX.com")
![\delta(q0, \epsilon, \epsilon)={(q1, \$)}](img/5bec03eece10818ad76e5c56e565f192.png "Rendered by QuickLaTeX.com")
![\delta(q1, \epsilon, a)={(q2, \epsilon)}](img/a589624d86f6d31b6b3f4af1dd00e6f1.png "Rendered by QuickLaTeX.com")
![\delta(q2, \epsilon, a)={(q2, a)}](img/6824431f97e003bbdc785d744b0ca614.png "Rendered by QuickLaTeX.com")
![\delta(q2, b, \$)={(q1, \$)}](img/010aefe1b7a24c769daef565f3f5d9a1.png "Rendered by QuickLaTeX.com")
![\delta(q1, \epsilon, \$)={(q3, \$)}](img/4c1d7db925eccd1dd86a036d38bf0d7d.png "Rendered by QuickLaTeX.com")给出

![](img/a035af3f1b370a6017d434e5361c7d8f.png)

让我们看看这个自动机是如何为 aabb 工作的。

<center>

| 排 | 状态 | 投入 | 过渡函数 | 队列(从左输入) | 移动后的状态 |
| --- | --- | --- | --- | --- | --- |
| one | q0 | 【T0 之二】【T1 之二 | δ(q0，a，ε)={(q0，a)} | a | q0 |
| Two | q0 | 一**一** bb | δ(q0，a，ε)={(q0，a)} | 嗜酒者互诫协会 | q0 |
| three | q0 | E | δ(q0，ε，ε)={(q1，$)} | $aa | 雌三醇环戊醚 |
| four | 雌三醇环戊醚 | E | d（q1， e， a）={（q2， e）} | 一美元 | q2 |
| five | q2 | E | δ(q2，ε，a)={(q2，a)} | 一美元 | q2 |
| six | q2 | aa **b** b | δ(q2，b，$)={(q1，$)} | 一美元 | 雌三醇环戊醚 |
| seven | 雌三醇环戊醚 | E | d（q1， e， a）={（q2， e）} | $ | q2 |
| eight | q2 | aab**b**的缩写形式 | δ(q2，b，$)={(q1，$)} | $ | 雌三醇环戊醚 |
| nine | 雌三醇环戊醚 | E | δ(q1，ε，$)={(q3，$)} | $ | q3 |

</center>