# 工程数学–偏导数

> 原文:[https://www . geesforgeks . org/engineering-数学系-偏导数/](https://www.geeksforgeeks.org/engineering-mathematics-partial-derivatives/)

A [功能](https://www.geeksforgeeks.org/types-of-functions-class-12-maths/)就像一台机器，接受一些输入，给出一个输出。*例如*，y = f(x)是‘x’中的一个函数。这里，我们说“x”是自变量，“y”是因变量，因为“y”的值取决于“x”。

**函数的一些例子有:**

1.  f(x) = x <sup>2</sup> + 3 是代数函数。
2.  e <sup>x</sup> 为指数函数。
3.  sin(x)，cos(x)，tan(x)，…等。都是三角函数。

现在，所有这些函数都是单个变量的函数，即只有一个自变量。

要理解偏导数的概念，首先要看二元函数是什么意思。
考虑一个 z = f(x，y)形式的函数，其中‘x’和‘y’是自变量，‘z’是因变量。这个函数叫做双变量函数。类似地，也可以定义几个变量(即有 2 个以上独立变量)的函数。

**多变量函数或多变量函数的一些例子有:**

1.f(x，y) = x <sup>2</sup> +y

2.f(x，y，z) = x-3y+4z

让我们通过图形来形象化这个概念。首先我们考虑单变量函数 f(x) = x <sup>2</sup> 。

![](img/89598b73220b2868a6a92d3edd1c7ef8.png)

f(x) = x^2 图

与单变量函数不同，我们不能将多变量函数可视化为二维图形。为此，我们将其绘制在三维平面上。例如，考虑 f(x，y) = x <sup>2</sup> +y <sup>2</sup> 的图形

![](img/0d2dd3ce5bb5a17bba86d316e159b9d2.png)

f(x，y) = x^2 + y^2 的曲线图

对于几个变量的函数，我们定义[极限](https://www.geeksforgeeks.org/formal-definition-of-limits/)如下:

![](img/0a62843faf796baa495c09060172e119.png)

这意味着，当‘x’接近‘a’和‘y’接近‘b’时，求 f(x)的极限。

类似地，连续性和[可微性](https://www.geeksforgeeks.org/differentiability-of-a-function-class-12-maths/)的[定义可以从单变量函数的定义扩展而来。](https://www.geeksforgeeks.org/mathematics-limits-continuity-differentiability/)

回想一下，单变量 y=f(x)函数的导数定义为:f’(x)= `![\frac{dy}{dx} ](img/7c83cafe394018ff80bd4213048ecbb5.png "Rendered by QuickLaTeX.com")

对于两个变量的函数 z = f(x，y)，我们将导数定义为:![\frac{\partial z}{\partial x}](img/5d4cb56361165b860f3dcb22d26e9a64.png "Rendered by QuickLaTeX.com")

这意味着通过保持“y”不变来计算函数“z”相对于“x”的导数。同样，我们可以通过保持‘x’不变来计算‘z’相对于‘y’的导数![\frac{\partial z}{\partial y}](img/3f0626e20aa95193fb3f046d8bf9dd07.png "Rendered by QuickLaTeX.com")

### **偏导数的几何解释**

![](img/5e84291cac67e3bf927e4fff27692684.png)

众所周知，对于单变量函数，导数的计算是通过曲线的切线的斜率。同样，我们可以理解多变量函数偏导数的几何解释。

考虑一个两个变量的函数，在三维平面上 z = f(x，y)，让平面 y=b 通过曲线 f(x，y)。

现在，我们画另一条曲线 f(x，b)，它位于垂直于平面 y=b 的 z 上。考虑这条曲线上的两个任意点 P，R，并画出穿过这些点的割线。

该割线的斜率使用如下第一原则计算:

![m = \frac{Δz}{Δx} = \frac{f(x+Δx,b)-f(a,b)}{Δx}](img/a46386ab6ec08fe02d55f90f6b64e5f4.png "Rendered by QuickLaTeX.com")

当这两个点彼此靠近时，差值δx 接近 0，我们以极限的形式计算出来:![\lim_{Δx\to0} \frac{Δz}{Δx} = \frac{f(a+Δx,b)-f(a,b)}{Δx}](img/16dbbd4bc91b82bc1dd7cdfc308c091e.png "Rendered by QuickLaTeX.com")

该极限是“z”相对于“x”的偏导数，将“y”视为常数，即

![\frac{\partial z}{\partial x} = \frac{f(a+Δx,b)-f(a,b)}{Δx}](img/361524eaffe4b8457814b73836bd33ad.png "Rendered by QuickLaTeX.com")

### 计算给定函数的偏导数。

计算给定函数偏导数的步骤:

1.  考虑 z = f(x，y)。
2.  通过将“y”视为常数，计算相对于“x”即![\frac{\partial z}{\partial x}   ](img/c92b78911a82e572fa6786c6aefa25ff.png "Rendered by QuickLaTeX.com")的偏导数，并对函数相对于“x”进行微分。
3.  通过将“x”视为常数，计算相对于“y”即![\frac{\partial z}{\partial y}   ](img/57ebf2cb4a97af953be0ecec73d2a3b0.png "Rendered by QuickLaTeX.com")的偏导数，并对相对于“y”的函数进行微分。

*例* : ![z = x^2 + y^2 + 3xy](img/6db83ea56cfd43d79ad82ddf2a0be14c.png "Rendered by QuickLaTeX.com")

这里，对于给定的函数，我们计算两个偏导数如下:

**情况 1** :通过将“y”视为常数，即![\frac{\partial z }{\partial x}](img/38ae1f582a9229697ceed1f2c181b9f0.png "Rendered by QuickLaTeX.com")来区分“x”

![](img/de4fd1dcee7df5b08d9a89593d2dae50.png)

通过处理“y”常量来区分“z”和“x”

**情况 2** :通过将“x”视为常数，即![\frac{\partial z }{\partial y}](img/cf8f0f4445e466499ababb73f3d42cc2.png "Rendered by QuickLaTeX.com")来区分“y”

![](img/5c35528ad32070f45d484e36d7ef7feb.png)

通过处理“x”常量来区分“z”和“y”

### 二阶偏导数

与计算单变量函数的二阶导数类似，我们也可以计算多变量函数的二阶导数。

例如，我们考虑相同的函数![z = x^2 + y^2 + 3xy  ](img/7dfc76adf5a3fca086e074c8ae1abf81.png "Rendered by QuickLaTeX.com")。

**案例 1** :我们再次区分![\frac{\partial z}{\partial x}   ](img/c92b78911a82e572fa6786c6aefa25ff.png "Rendered by QuickLaTeX.com")和【x】

![](img/0498b5a7cd520d130078568d3f5f9f07.png)

**案例 2** :我们再次区分![\frac{\partial z}{\partial y}   ](img/57ebf2cb4a97af953be0ecec73d2a3b0.png "Rendered by QuickLaTeX.com")和‘y’

![](img/08fefa9b8170825dd1d0c5b8eebd7927.png)

**案例 3** :我们再次区分![\frac{\partial z}{\partial x}   ](img/c92b78911a82e572fa6786c6aefa25ff.png "Rendered by QuickLaTeX.com")与“y”

![](img/a17a9b5becb36887a88b5f362ecd678f.png)

**案例 4** :我们再次区分![\frac{\partial z}{\partial y}   ](img/57ebf2cb4a97af953be0ecec73d2a3b0.png "Rendered by QuickLaTeX.com")和【x】

![](img/c270879d1ad31c993bc462580903b356.png)