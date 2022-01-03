# 配对 T 检验–详细概述

> 原文:[https://www . geesforgeks . org/painted-t-test-a-detailed-overview/](https://www.geeksforgeeks.org/paired-t-test-a-detailed-overview/)

学生 t 检验或 t 检验是用于确定两个样本平均值之间是否有差异的统计方法。测试通常是为了找出实验中是否存在任何采样错误或不太可能。根据您的数据和结果需要，该 t 检验进一步分为 3 种类型。类型有:

*   **T test of a sample:** Here, the average value of a single population is compared with the known average value.
*   **independent sample t test:** here, compare the mean values of two different populations.
*   **T test of paired samples:** Here, the mean value of the same population or population is at different times.

在本文中，我们将概述配对 t 检验:

### 什么是配对 t 检验？

配对 t 检验有助于数据分析比较来自同一数据集的两个平均值，以确定差异是否为零。在配对 t 检验的统计过程中，也称为相依样本 t 检验，每个数据集，比如个人、单位或物体，被测量两次，从而为配对 t 检验提供成对的观察。简单来说，这个测试是用来发现因变量的平均值在两个相同或相关的组中是否相同。例如:测量一个人早餐前后的体重。

### 它是如何工作的？

要进行配对 t 检验，您必须遵守配对 t 检验的以下假设:

*   数据的因变量应该是连续的(必须分成区间或比率水平或区间)
*   观察必须相互独立，这是一个随机的数据样本应该做的。
*   配对 t 检验只能对相关样本或组实施。每个样本或组的主题必须相同。
*   配对 t 检验中使用的因变量数据必须没有异常值。
*   因变量应该是正态(近似)分布的。

遵循这些假设将帮助你找到一个更可靠的结果。

### 配对 t 检验公式:

在进入配对 t 检验的公式之前，你必须了解这个检验所遵循的假设。配对 t 检验有两种相互竞争的假设，即零假设和替代假设。

零假设假设成对样本的平均值之差等于零。相反，替代假设假设配对样本之间的平均差异不等于零。替代假设还具有基于低尾或高尾结果的扩展。

**假设**可以表示为:

**零假设，H0** : u1 = u2 或者 H0:u1–U2 = 0

**替代假设**、 **H1** : u1 不等于 u2 或者**H1**:u1–U2 不等于零。

这里，

*   **U1** is the average value of variable 1.
*   Is the average of variable 2 [U2] is a variable in the population.

配对 t 检验的计算方法如下:

**【t = m/(s/√n)**

其中:

*   **m** = mean value
*   **s** = standard deviation of difference (d)
*   **n** = the size of d

可以使用[配对 t 检验计算器](https://statsjournal.com/paired-t-test)快速得出结果。寻找一个在线的 t-test 计算器，它可以为您提供一步一步的解决方案，同时提供有保证的准确结果。

### 成对测试 v/s 不成对 t-测试

配对 t 检验用于发现总体中两个相依样本的平均值之间是否存在显著差异。另一方面，不成对 t 检验(一个样本和独立样本 t 检验)用于确定两个独立样本之间是否存在显著的均值差异。

在配对样本的情况下，组之间的关系存在，因为样本取自不同老年人的同一组，而独立样本 t 检验比较两个不相关组的平均值。

在配对 t 检验中，假设方差不相等，并且实现零假设，而在配对 t 检验的情况下，假设样本之间的方差相等。

### 常见问题:

**哪里可以实现配对 t 检验？**

配对 t 检验通常用于确认工业或产品领域产品的质量或影响。它用于在间隔后对同一组进行两次测试。解释在现实世界中哪里可以使用配对 t 检验的一些例子是:

*   Test the quality of food during fresh baking and after one month.
*   Test the immediate effect of a new drug on a group of people, and then the long-term effect on the same group of people.
*   Test the pulse rate of a group of people before and after the marathon.

**你应该使用成对还是不成对的 t 检验？**

如果你仔细遵循 t 检验假设和说明，为你的数据选择正确的 t 检验并不难。记住数据类型在成对和不成对的 t-test 实现之间没有太多的选择。对于配对 t 检验，你必须有一个自然配对，创建一个匹配配对或重复测量。