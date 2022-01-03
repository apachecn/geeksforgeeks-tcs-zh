# 偏导数的应用–两个变量的最大值和最小值

> 原文:[https://www . geesforgeks . org/应用偏导数双变量最大值和最小值/](https://www.geeksforgeeks.org/application-of-partial-derivative-two-variable-maxima-and-minima/)

偏导数可以用来求双变量函数的最大值和最小值(如果存在的话)。我们试图找到一个斜率为零的静止点，然后追踪它附近的最大值和最小值。最大值/最小值的实际应用是给定曲线的利润最大化或损失最小化。

设 f(x，y)为实值函数，设(pt，pt’)为 f(x，y)域内的内点，则

*   Pt, pt' is called the local maximum point. If there is h > 0, then f(pt, pt')≥f(x, y). For all the values of x, x≠a f(pt, pt') in (pt–h, pt'+h), it is called the local of f(x, y).
*   Pt, pt' If h < 0 makes f(pt, pt') ≥f(x, y), for all x in (pt–h, pt'+h), x≠a, the value of the local minimum point f(pt, pt') is called the local minimum of f(x, y)

**求双变量函数最大值和最小值的算法:**

1.  With **F <sub>XX</sub> = 0** and **F <sub>YY</sub> = 0** **Note** : F <sub>XX</sub> and F <sub>YY</sub> are respectively 】
2.  The obtained result will be regarded as the **stationary/turning point** of the curve.
3.  Create three new variables R, T and S.
4.  使用 **r=f <sub>xx、</sub> t=f <sub>yy</sub> 找到 r、t、s 的值，s = f <sub>xy</sub> T33**

**If**

**rt-s<sup>2</sup>)|<sub>(固定 pts)</sub> > 0** 
**(最大值/最小值)存在**
8.  If(rt-s <sup>2</sup> )| <sub>(固定</sub>pts)<0(否

**示例-1 :**

函数 f(x，y)= x<sup>2</sup>y 3xy+2y+x 有

*   (a) No local extremum
*   (b) A local minimum but no local maximum
*   (c) A local maximum but no local minimum.
*   (d) a local minimum and a local maximum

**说明:**

回答:A

```
r=∂2f/∂x2=2y
s=∂2f/∂x∂y=2x−3
t=∂2f/∂y2=0
```

因为，rt-s<sup>2</sup>≤0，(如果 rt-s <sup>2</sup> < 0，那么我们没有最大值或最小值，如果= 0，那么我们什么也不能说)。

当 rt s<sup>2</sup>>0 和 r < 0 时，最大值将存在。

当 rt-s<sup>2</sup>>0 和 r > 0 时，将存在最小值。

**由于 rt s<sup>2</sup>永远不大于 0，所以我们没有局部极值。**

**示例-2 :**

求函数 f(x，y)= 2x<sup>2</sup>+2xy+2y<sup>2</sup>–6x

```
fx(x,y) = 4x + 2y - 6=0    (1)
fy(x,y) = 2x + 4y=0        (2)
```

的局部最小值

在求解(1)和(2)时，我们得到，

```
x=2,y=-1
r=∂2f/∂x2=4
s=∂2f/∂x∂y=2
t=∂2f/∂y2=4
rt−s2=12
```

**As rt s<sup>2</sup>0 和 r > 0。因此，(2，-1)是局部极小点。**

**示例-3 :**

求 f(x，y) = x 的最大值/最小值 <sup>2</sup> +y <sup>2</sup> + 6x +12

```
fx(x,y) = 2x+6=0     (1)
fy(x,y) = 2y=0       (2)
```

在求解(1)和(2)时，我们得到，

```
x=-3,y=0
r=∂2f/∂x2=2
s=∂2f/∂x∂y=0
t=∂2f/∂y2=2
```

**As rt s<sup>2</sup>0 和 r > 0。因此，(-3，0)是局部极小点。**