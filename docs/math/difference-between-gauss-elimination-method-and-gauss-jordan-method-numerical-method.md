# 高斯消元法与高斯乔丹法的区别|数值法

> 原文:[https://www . geesforgeks . org/gauss-消元法与 gauss-Jordan-method-numeric-method 之差/](https://www.geeksforgeeks.org/difference-between-gauss-elimination-method-and-gauss-jordan-method-numerical-method/)

**高斯消去法:**

高斯消元法是应用最广泛的方法之一。这种方法是一个从线性方程中消除未知数的系统过程。该方法分为两个线性方程:

*   三角化方法
*   反向替代法

**高斯乔丹法:**

高斯乔丹法是对高斯消去法的一点修改。这里，在消除阶段，系数以这样一种方式被消除，即方程组被简化为对角矩阵。高斯乔丹法的第一种方法是从除第一个方程之外的所有方程中去掉第一个变量，即 x。然后它从除第二个方程之外的所有方程中消除第二个变量，即 x2，以此方式继续，最后我们从除最后一个方程之外的所有方程中消除最后一个变量，即 in。

<figure class="table">

| Sr.No | 高斯消去法 | 高斯乔丹法 |
| --- | --- | --- |
| 1. | 在这种方法中，未知量被连续地消除，系统被简化为一个上三角系统，未知量通过反向替换从该系统中被发现。 | 在这种方法中，通过所有方程来消除未知数，而不仅仅是从后面的方程。因此，系统最终简化为对角矩阵形式，即每个方程只包含一个未知数。 |
| 2. | 求 n 个联立线性方程的解，乘法和除法的次数是相同的。n3/3。**例如:**如果 n=5，则乘法和除法 ISI 消除的次数大约为 42。 | 求 n 个联立线性方程的解，乘法和除法的次数是相同的。n3/2。**例如:**如果 n=5，乘法和除法的次数大约为 62。 |
| 3. | 这看起来并不容易，但比高斯乔丹法所需的运算量要少 50%左右。 | 这似乎更容易，但需要的操作比高斯消去法少 50%左右。 |
| 4. | 对于大系统，高斯消元法不是首选。 | 对于大系统，高斯乔丹法优于高斯消去法 |

</figure>