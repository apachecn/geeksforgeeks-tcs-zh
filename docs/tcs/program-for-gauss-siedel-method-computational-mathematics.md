# 高斯塞德尔方法程序(计算数学)

> 原文:[https://www . geesforgeks . org/program-for-gauss-siedel-method-computational-mathematics/](https://www.geeksforgeeks.org/program-for-gauss-siedel-method-computational-mathematics/)

**高斯赛德尔**方法是求解(多个)线性方程组的一个迭代过程。这也是著名的**‘利伯曼’**方法。在数值分析的任何迭代方法中，每一次解的尝试都是从方程的近似解开始的，并进行迭代，直到获得所需的精度。在高斯-塞德尔方法中，在连续迭代中使用最近的值。高斯-塞德尔方法允许用户控制舍入误差。
高斯赛德尔法与雅可比法非常相似，被称为连续位移**法**。(因为最近获得的值被用在随后的等式中)。高斯赛德尔收敛准则取决于以下两个性质:(必须满足)。

*   矩阵是对角占优的。
*   矩阵是对称的正矩阵。

**涉及的步骤:**

*   第一步:计算 Xi 所有线性方程的值。(初始阵列必须可用)
*   第二步:计算每个 Xi，并重复上述步骤。
*   第三步:利用每一步后的绝对相对近似误差，检查误差是否出现在预先规定的公差范围内。

高斯赛德尔法代码:

## C

```
#include <stdio.h>

int main()
{
    int count, t, limit;
    float temp, error, a, sum = 0;
    float matrix[10][10], y[10], allowed_error;

    printf("\nEnter the Total Number of Equations:\t");
    scanf("%d", & limit);
    // maximum error limit till which errors are considered,
    // or desired accuracy is obtained)

    printf("Enter Allowed Error:\t");
    scanf("%f", & allowed_error);
    printf("\nEnter the Co-Efficients\n");

    for(count = 1; count < = limit; count++)
    {
        for(t = 1; t < = limit + 1; t++)
        {
            printf(" Matrix[%d][%d] = " , count, t);
            scanf(" %f" , & matrix[count][t]);
        }
    }

    for(count = 1; count < = limit; count++)
    {
        y[count] = 0;
    }
    do
    {
        a = 0;
        for(count = 1; count < = limit; count++)
        {
            sum = 0;
            for(t = 1; t  a)
            {
                a = error;
            }
            y[count] = temp;
            printf("\nY[%d]=\t%f", count, y[count]);
        }
        printf("\n");
    }
    while(a > = allowed_error);

    printf("\n\nSolution\n\n");

    for(count = 1; count < = limit; count++)
    {
        printf(" \nY[%d]:\t%f" , count, y[count]);
    }
    return 0;
}
```

**输出:**

```
Enter the Total Number of Equations:   1
Enter Allowed Error:   0.5

Enter the Co-Efficients
Matrix[1][1] = 1
Matrix[1][2] = 4

Y[1]=   4.000000

Y[1]=   4.000000

Solution

Y[1]:   4.000000  
```

**优势:**T2】

*   更快的迭代过程。(不同于其他方法)
*   简单易实现。
*   内存需求低。

**劣势:**T2】

*   收敛速度较慢。(不同于其他方法)
*   需要大量迭代才能到达收敛点。