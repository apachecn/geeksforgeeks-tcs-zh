# 排列组的顺序

> 原文:[https://www.geeksforgeeks.org/order-of-permutation-group/](https://www.geeksforgeeks.org/order-of-permutation-group/)

**排列顺序-:** 对于给定的排列 P，如果 **P <sup>n</sup> = I** (同一性排列)，那么 n 就是排列顺序。

让一个排列![P=\begin{pmatrix} a & b & c\\ d & d & e \end{pmatrix}](img/ed92af6e9bc8d76347952f0f4454e297.png "Rendered by QuickLaTeX.com")

和**P<sup>n</sup>= I =**T4】

那么 **n** 就是排列的顺序。

**例 1-:** 多少次![\begin{pmatrix} 1 & 2 & 3&4\\ 1 & 3 & 4&2 \end{pmatrix}   ](img/893b0e8e91755458e22cc2bf0cf087f6.png "Rendered by QuickLaTeX.com")被自身相乘产生![\begin{pmatrix} 1 & 2 & 3&4\\ 1 & 2 & 3&4 \end{pmatrix}](img/1609ead0539fad74db78836b4f09d1d5.png "Rendered by QuickLaTeX.com")

**解-:** 让**P =**T4】

然后 **P <sup>2</sup> =P.P=** ![\begin{pmatrix} 1 & 2 & 3&4\\ 1 & 3 & 4&2 \end{pmatrix}\begin{pmatrix} 1 & 2 & 3&4\\ 1 & 3 & 4&2 \end{pmatrix}](img/06ea628f4f09e1018430b138acb24680.png "Rendered by QuickLaTeX.com")

**P<sup>2</sup>=**T4】

**P <sup>3</sup> = P <sup>2</sup> 。P=** ![\begin{pmatrix} 1 & 2 & 3&4\\ 1 & 4 & 2&3 \end{pmatrix}\begin{pmatrix} 1 & 2 & 3&4\\ 1 & 3 & 4&2 \end{pmatrix}](img/4dc78d919df682f344bc2dd5e4381899.png "Rendered by QuickLaTeX.com")

**P<sup>3</sup>=**T4】=我

因此所需的数字是 3。

**订单=3**

**例 2-:** 求排列顺序![\begin{pmatrix} 1 & 4 & 2&6\\ \end{pmatrix}   ](img/042bd37f72b5abb21d64dc04fb493ccf.png "Rendered by QuickLaTeX.com")。

**解-:** 让给定的排列为 P= ![\begin{pmatrix} 1 & 4 & 2&6\\ \end{pmatrix}](img/64bb8b0de001f8470ab68be43babadf0.png "Rendered by QuickLaTeX.com")

我们可以把 P 写成 P= ![\begin{pmatrix} 1 & 4 & 2&6\\ 4 & 2 & 6&1 \end{pmatrix}](img/bcc8dca866b02000f03bcf6de3a8bf04.png "Rendered by QuickLaTeX.com")

P <sup>2</sup> = ![\begin{pmatrix} 1 & 4 & 2&6\\ 4 & 2 & 6&1 \end{pmatrix} \begin{pmatrix} 1 & 4 & 2&6\\ 4 & 2 & 6&1 \end{pmatrix}](img/23f7c5a885115f7cf2ee55afed34ed81.png "Rendered by QuickLaTeX.com")

= ![\begin{pmatrix} 1 & 4 & 2&6\\ 2 & 6 & 1&4 \end{pmatrix}](img/ef1dcb54d1629fac7b457c9827942ba7.png "Rendered by QuickLaTeX.com")

P <sup>3</sup> =P <sup>2</sup> 。P= ![\begin{pmatrix} 1 & 4 & 2&6\\ 2 & 6 & 1&4 \end{pmatrix}\begin{pmatrix} 1 & 4 & 2&6\\ 4 & 2 & 6&1 \end{pmatrix}](img/ce61bde0df91f90d9b2feaacaa3aa1d3.png "Rendered by QuickLaTeX.com")

= ![\begin{pmatrix} 1 & 4 & 2&6\\ 6 & 1 & 4&2 \end{pmatrix}](img/c65ee9b33e6f265c5208596c3223454b.png "Rendered by QuickLaTeX.com")

P <sup>4</sup> =P <sup>3</sup> 。P= ![\begin{pmatrix} 1 & 4 & 2&6\\ 6 & 1 & 4&2 \end{pmatrix}\begin{pmatrix} 1 & 4 & 2&6\\ 4 & 2 & 6&1 \end{pmatrix}](img/e2161bd55f703224b614afaaab2e6c36.png "Rendered by QuickLaTeX.com")

= ![\begin{pmatrix} 1 & 4 & 2&6\\ 1 & 4& 2&6 \end{pmatrix}](img/51b9a16f62d8d95a8fdf1f086cf29fb9.png "Rendered by QuickLaTeX.com")

P <sup>4</sup> =I(身份置换)

**因此，顺序为 4。**