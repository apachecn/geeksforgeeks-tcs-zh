# 帕里克定理

> 原文:[https://www.geeksforgeeks.org/parikhs-theorem/](https://www.geeksforgeeks.org/parikhs-theorem/)

**引言:**
理论计算机科学中的帕里克定理说，如果只看上下文无关语言中每个终端符号的出现次数，而不考虑它们的顺序，那么这种语言与常规语言是无法区分的。这对于确定具有给定数量的终端的字符串不被上下文无关的语法所接受是有用的。它于 1961 年由罗希特·帕里克首次证明，并于 1966 年重新出版。

**定理:**
”**帕里克定理**”指出，上下文无关语言的帕里克图像是半线性的，或者等效地说，每种上下文无关语言都有与某种常规语言相同的帕里克图像。我们提出了一个非常简单的结构，在给定上下文无关语法的情况下，产生了一个识别这种规则语言的有限自动机。
利用上下文无关语言的泵引理的一种强化形式给出了 Parikh 定理的一个简单证明。

**1.帕里赫图片 –**

*   如果 w 是某个σ上的一个词，我们用π<sub>∑</sub>(w)表示 w 在字母表σ上的 Parikh 像。
*   π<sub>∑</sub>(w)将σ中的字符映射到 w 中的出现次数。
*   σ上语言 L 的 Parikh 映象是{π<sub>∑</sub>(w)| w∈L }。用π<sub>∑</sub>(L)表示。

**示例–**

1.  π<sub>{ a，b，c}</sub> (bccba) = (1，2，2)，其中(1，2，2)代表{(a，1)，(b，2)，(c，2)}。
2.  π<sub>{ a，b，c}</sub> (cabaaabb) = (4，3，1)。

**2。推导–**
让∑={a1，a2，…，ak}成为一个字母表。单词的 Parikh 向量定义为函数 p:∞*->N<sup>k</sup>，由 p(w) = (|w| <sub>a1、</sub> |w| <sub>a2、</sub> …、|w| <sub>k)</sub> 给出，其中|w| <sub>ai</sub> 表示单词 w 中字母 a <sub>i</sub> 的出现次数。

*   **语句 1–**
    让 L 成为上下文无关的语言。设 P(L)为 L 中单词的 Parikh 向量的集合，即 P(L)={p(w) | w ∈ L}。那么 P(L)就是一个半线性集合。
    半线性集=可预定义的 N <sup>k</sup> 子集。
    如果两种语言具有相同的 Parikh 向量集，则称它们是交换等价的。
*   **语句 2–**
    如果 S 是任何半线性集合，那么 Parikh 向量在 S 中的词的语言在交换上等价于某种正则语言。因此，每种上下文无关的语言在交换上都等价于某种常规语言。
    这两个等价的说法可以归结为:上下文无关语言和正则语言的 p 下的像是一样的，它等于半线性集的集合。

**对于有界语言:**
如果 L 是 w1 的子集，则语言 L 是有界的……..wk*对于一些固定单词 w1，…..wk。金斯伯格和斯巴涅尔给出了有界语言的一个充要条件，类似于帕里克定理。
金斯堡-斯巴涅尔定理说有界语言 L 是上下文无关的当且仅当{(n1，…。，nk) | w1n1…… wknk ∈ L}是分层的半线性集合。

**示例–**

*   **上下文无关语言(CFL)L = { 0<sup>N</sup>1<sup>N</sup>| N>= 1 }**T6】0 的个数(N<sub>0</sub>)= N
    1 的个数(N<sub>1</sub>)= N
    N<sub>0</sub>= N<sub>1</sub>T17】这里让字符串 w = '000111 '因此，N <sub>0</sub> = N <sub>1</sub> ，因此，w ∈ L 和这个字符串满足上下文无关语言的一个属性。
    Parikh 定理是计算给定字符串中每个输入符号的出现次数，这里我们计算 0 的个数和 1 的个数。
    **Parikh 向量**可以用字符串中 0(|w| <sub>0</sub> )和 1(|w| <sub>1</sub> )的个数来定义这个特定字符串。
    P(w) = {|w| <sub>0</sub> ，|w| <sub>1</sub>

**帕里克矢量:**
P('000111') = {3，3}

*   这里还有一个例子。Let，L = {0 <sup>n</sup> 1 <sup>n</sup> | n < 3，n > =1}。n 的可能值是 1 和 2。
    对于 n = 1，字符串为‘01’，对于 n = 2，字符串为‘0011’。

**Parikh 向量**可以用字符串中的 0(|w| <sub>0</sub> )和 1(|w| <sub>1</sub> )来定义。
P(w) = {|w| <sub>0</sub> ，|w| <sub>1</sub> }
所以，P('01') = {1，1}
同样，P('0011') = {2，2}
**P(L)是 L 中单词的 Parikh 向量的集合。**
**那么，这里 P(L) = { P('01 ')，P('01) 所以属于给定语言的字符串是有限的，我们可以很容易地为给定语言构造 DFA，即与某种正则语言的交换等价。**

**一些推论:**

*   *每一个 CFL 都是**“字母等价物”**到一种常规语言*。
    例如:ψ({ a<sup>n</sup>b<sup>n</sup>| n≥0 })=ψ((ab)<sup>*</sup>)。
*   *CFL 的长度形成一个最终的周期集。*
*   CFL 的单字母字母表是有规律的。
*   *这对于确定具有给定数量的终端的字符串不被上下文无关语法接受是有用的。*

**意义:**
这个定理有多种解释。它表明，单一字母表上的上下文无关语言必须是常规语言，某些上下文无关语言只能有不明确的语法。这种语言被称为固有的模糊语言。从形式语法的角度来看，这意味着一些模棱两可的上下文无关语法不能转换为等价的明确上下文无关语法。