# 正则表达式和正则语言的星高

> 原文:[https://www . geesforgeks . org/star-height-正则表达式-正则语言/](https://www.geeksforgeeks.org/star-height-regular-expression-regular-language/)

**星高**涉及计算理论领域。它用来表示正则表达式和正则语言的结构复杂性。这里的复杂性，与正则表达式中克莱尼星的最大嵌套深度有关。
这里需要注意的是，一种常规语言可能由不唯一但等价的常规表达式来表示。这些正则表达式可能有不同的星形高度，这取决于它们的结构复杂性(即嵌套)。但是**正则语言的星高是一个唯一的数字，等于代表该语言的任何正则表达式的最小星高。**在本文中**广义恒星高度**是一个合适的术语，它定义了克莱尼恒星的最小嵌套深度，以通过广义正则表达式来描述语言。例如:

字母表集合{a，b}上的语言“aba”可以使用正则表达式生成，

```
(a + b)* ...... (1) Star height = 1
(a* b*)* ...... (2) Star height = 2
```

但是我们考虑最小的恒星高度。因此常规语言“aba”的星高是一。

**恒星高度也被定义为正则表达式中出现的克莱尼恒星的最大嵌套深度。**为了正式陈述恒星高度，正则表达式的“h”可以写成，

h( ![\phi](img/2e8a7ac66542317be45c695ae849580d.png "Rendered by QuickLaTeX.com") ) = 0，其中![\phi](img/2e8a7ac66542317be45c695ae849580d.png "Rendered by QuickLaTeX.com")是空集合
h( ![\epsilon](img/9e0d0faaeb36399f71c3ccdd6c2b69d0.png "Rendered by QuickLaTeX.com") ) = 0，其中![\epsilon](img/9e0d0faaeb36399f71c3ccdd6c2b69d0.png "Rendered by QuickLaTeX.com")是空字符串
h(t) = 0，其中 t 可以是字母表集合
h(EF) = max(h(E)，h(F))，其中 E，F 表示正则表达式
h(E*) = h(E) + 1

一些例子是:

*   h(a*(b a*)*) = 2
*   h((a b*) + (a* a b*)*b)*) = 3
*   h(a) = 0

Eggan 教授试图给出接受语言 L 的自动机的循环复杂度和语言的星高 L
**之间的关系语言的星高 L 等于接受的自动机的最小循环复杂度， L.** 还可以说，既是**可访问的(即通过删除所有不可访问的状态和到或来自它们的任何转换而构建的自动机)**又是**共同可访问的(即，如果存在将我们从 q 带到标记状态的字符串 s，则自动机的状态 q 被称为是共同可访问的)**的自动机的循环复杂度是通过状态消除方法(或 BMC 算法)的不同可能执行而获得的正则表达式的星高的最小值。

很明显，一种恒星高度为零的正则语言只能代表有限数量的正则语言。广义星高认为取正则表达式的补码不会导致星高的增加。这种考虑产生了有趣的结果。

例如–考虑一组字母{x，y}。正则语言“所有以 x 开头和结尾的字符串”的正则表达式的星形高度，即

```
h(x(x + y)*x+x) = 1, since only one level of Kleene nesting exists
```

但是同样的语言也可以用正则表达式 x ![\phi](img/2e8a7ac66542317be45c695ae849580d.png "Rendered by QuickLaTeX.com") ^c x + x 来表示，因为![\phi](img/2e8a7ac66542317be45c695ae849580d.png "Rendered by QuickLaTeX.com") ^c 表示输入字母上的所有字符串的集合。

```
Now, h(x ^c x + x) = 0, as no Kleene nesting present
```

**因此，语言的广义星高是 0，即使它的星高是 1。**