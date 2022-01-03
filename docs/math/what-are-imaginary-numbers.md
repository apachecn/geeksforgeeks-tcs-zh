# 什么是虚数？

> 原文:[https://www.geeksforgeeks.org/what-are-imaginary-numbers/](https://www.geeksforgeeks.org/what-are-imaginary-numbers/)

如果你想知道什么是虚数，并认为虚数一定有意义，那么让我们进入这篇文章，了解什么是虚数。

**虚数:**
虚数是平方后得出负数的数。虚数是负数的平方根，它们没有任何确定的值。
虚数表示为实数和虚数的乘积 **i** 。

**示例–**

```
3i, 5i, 25i are some examples of imaginary numbers.
```

i <sup>2</sup> 的值为-1。
所以(5i) <sup>2</sup> 的值是-25，这意味着![\sqrt{-1}  ](img/506913b3ed0bb758430eb4990e3acf77.png "Rendered by QuickLaTeX.com")是 **i.**

**复数:**
复数是实数和虚数的组合。
复数的标准形式是-a+bi。
其中 a 和 b 是实数。I 是一个假想的单位。
现在我们通过一些例子来快速了解一下:

1.  **实数–**
    -1，2，10，10000。
2.  **虚数–**
    4i，-5i，2400i。
3.  **复数–**
    2+3i，-5-4i。

**一个虚数的共轭对:**

*   a+bi 是复数， **a +bi** 的共轭对是 **a-bi** 。
*   当一个虚数乘以它的共轭对时，结果将是一个实数。

**虚数法则:**

1.  ![i = \sqrt{-1}](img/db894d06a991187df136a946b4feb8da.png "Rendered by QuickLaTeX.com")
2.  ![i^2 = -1](img/b019ec1e813c7c72c002a292e95e3095.png "Rendered by QuickLaTeX.com")
3.  ![i^3 = -i](img/a90f515101a574b59e4655351388e460.png "Rendered by QuickLaTeX.com")
4.  ![i^4 = 1](img/d0d2c90cb9ed94f6e075669f21ec8e76.png "Rendered by QuickLaTeX.com")
5.  ![i^{4n} = 1](img/13ad1ec190bdf721091eb937e1d0336d.png "Rendered by QuickLaTeX.com")

**虚数算术运算:**
**1。添加–**

*   两个虚数相加，然后实部加一，再虚部加一。

**示例–**

**1。**(2+2i)+(3+4i)
=(2+3)+(2+4)I
=(5+6i)

**2。**(3+4i)+(5+3i)
=(8)+(7)I
= 8+7i

**3。**(5+3i)+(4+2i)
=(5+4)+(3+2)I
= 9+5i。

**2。减法–**

*   两个虚数相减，然后实部相减，然后虚部相减。

**示例–**

**1。**(2+2i)–(3+4i)
=(2–3)+(2–4)I
=(-1–2i)

**2。**(3+4i)–(5+3i)
=(-2)+(1)I
=-2+I

**3。**(5+3i)–(4+2i)
=(5–4)+(3–2)I
= 1+I。

**3 .乘〔t1〕**

*   当两个虚数相乘时，结果如下

**示例–**

**1 .**(a+bi)(c+di)
=(a+bi)c+(a+bi)
= AC+BCI+ADI+![bdi^2 ](img/9682c930ea901f4e07ee811877bc9285.png "Rendered by QuickLaTeX.com")
=(AC–BD)+I(BC+ad)

**2。**(3+4i)*(3–4i)
=(9+12i-12i–16![i^2 ](img/e42475b5f90fffc586de903a7d888c6d.png "Rendered by QuickLaTeX.com"))
= 25

**3。**(2+2i)*(3–4i)
=(6+6i-8i–8![i^2 ](img/e42475b5f90fffc586de903a7d888c6d.png "Rendered by QuickLaTeX.com"))
=(14–2i)

**4)除法**
分子和分母将乘以它的共轭分母对。

**示例–**

**1。** (2 + 2i) / (3 + 4i)
将分子和分母乘以分母的共轭对。
=(2+2i)*(3–4i)/(3+4i)*(3–4i)
=(6+6i-8i–8![i^2 ](img/e42475b5f90fffc586de903a7d888c6d.png "Rendered by QuickLaTeX.com"))/(9+12i-12i–16![i^2 ](img/e42475b5f90fffc586de903a7d888c6d.png "Rendered by QuickLaTeX.com"))
=(14–2i)/25

**2。** (3 + 4i) / (2 + 2i)
将分子和分母乘以分母的共轭对。
=((3+4i)*(2–2i))/((2+2i)*(2–2i))
=(6+2i–8![i^2 ](img/e42475b5f90fffc586de903a7d888c6d.png "Rendered by QuickLaTeX.com"))/(4-4![i^2 ](img/e42475b5f90fffc586de903a7d888c6d.png "Rendered by QuickLaTeX.com"))
=(14+2i)/(8)
=(7+I)/4

**3。** (2 + 2i) / (2 + 2i)
将分子和分母乘以分母的共轭对。
=((2+2i)*(2–2i))/((2+2i)*(2–2i))
=(4–4![i^2 ](img/e42475b5f90fffc586de903a7d888c6d.png "Rendered by QuickLaTeX.com"))/(4–4![i^2 ](img/e42475b5f90fffc586de903a7d888c6d.png "Rendered by QuickLaTeX.com"))
= 8/8
= 1

**我们在哪里使用虚数:**

*   虚数在各种数学证明中非常有用。
*   虚数用来表示波。
*   虚数出现在不接触 x 轴的方程中。
*   虚数在高等微积分中非常有用。
*   合成交流电流非常困难，因为它们在波上可能不匹配。
*   使用虚电流有助于简化计算。