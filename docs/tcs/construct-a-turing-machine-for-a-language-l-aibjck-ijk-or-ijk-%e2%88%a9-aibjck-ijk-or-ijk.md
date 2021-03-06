# 为语言构建图灵机 L = { aibjk | I<j or="" i="">j>k }∩{ aibjk | I>j>k 或 I>j>k }</j>T3】

> 原文:[https://www . geesforgeks . org/construct-a-turing-机器换语言-l-aibjk-ijk-or-ijk-% E2 % 88% a9-aibjk-ijk-or-ijk/](https://www.geeksforgeeks.org/construct-a-turing-machine-for-a-language-l-aibjck-ijk-or-ijk-%e2%88%a9-aibjck-ijk-or-ijk/)

先决条件–[图灵机](https://www.geeksforgeeks.org/turing-machine/)

语言 L = { a<sup>I</sup>b<sup>j</sup>c<sup>k</sup>| I<j<k 或 I>j>k }∩{ a<sup>I</sup>b<sup>j</sup>c<sup>k</sup>| I>j>k 或 i > j > k}与语言 L={a <sup>i 每一串“a”、“b”和“c”都有一定数量的“a ”,然后是一定数量的“b ”,然后是一定数量的“c”。</sup> 

*   第一个符号的计数至少应为 1。此后“b”和“c”可以有同样多，但 a 的计数小于“b”的计数，“b”的计数小于“c”的计数。
*   并且，第三个符号的计数应该至少为 1。此后“a”和“b”可以一样多，但是 c 的计数小于“b”的计数，而“b”的计数小于“a”的计数
*   结论:第二个符号的计数必须大于第一个和第三个符号的最大计数，第一个和第三个符号的计数可以相等，也可以不相等
    1.  通过将两个元素作为一个元素来比较两个元素。
    2.  如果|Second|大于 max(|First|，|Third|)，则接受它。
    3.  否则不接受。
    4.  **步骤-1:** 将 A 转换为 X，向右移动，转到步骤 2。如果找到 Y，忽略它，并向右移动到步骤-5。

    5.  **第二步:**继续忽略 A 和 Y，向右移动。将 D 转换为 Y，然后向右移动并转到步骤 3。
    6.  **第三步:**继续忽略 D 和 Z，向右移动。如果找到了 C，把它变成 Z，向左移动到第 4 步。如果找到 B，忽略它，向左移动，转到步骤 8。
    7.  **第四步:**继续忽略 Z、A、Y、D，向左移动。如果找到了 X，忽略它并向右移动，转到步骤 1。
    8.  **第五步:**继续忽略 Y，向右移动。如果找到了 D，把它变成 Y，然后向右移动到第 6 步。
    9.  **第 6 步:**继续忽略 D 和 Z，向右移动。将 C 转换为 Z，向左移动并转到步骤 7。如果忽略它，向左移动并转到步骤 11。
    10.  **第 7 步:**继续忽略 D 和 Z，向左移动。如果找到 Y，忽略它并向右移动，转到步骤-5。
    11.  **第 8 步:**继续忽略 D、Y、A，向左移动。忽略 X 向右移动，转到步骤 9。如果 D 忽略并向右移动，转到步骤-11
    12.  **步骤-9:** 将 A 转换为 X，向右移动，转到步骤-10。
    13.  **第 10 步:**继续忽略 Y 和 A，向右移动。如果 D 变成 Y，向右移动，转到第 8 步。
    14.  **步骤 11:** 停止机器(接受字符串)。
    15.  使用 Q0，当找到 A 时，将其设为 X，然后向右移动并陈述 Q1。当发现 Y 时，忽略它，转到右侧，进入状态 Q4
    16.  在 Q1 州，忽略所有的 A 和 Y，转到右边。如果找到了，就做 Y，直接去下一个州 Q2。
    17.  在 Q2，忽略所有的 D，Z，向右移动。如果发现 B，忽略它，向左移动，转到状态 Q4，如果发现 C，让它向左移动，转到状态 Q3。
    18.  在 Q3 状态下，忽略所有 Z、D、Y、A，向左移动。如果发现 X，忽略它，向右移动到 Q0。
    19.  在第四季度，忽略所有 Y 并向右移动。如果找到 D，将其变为 Y，并向右移动到 Q5。
    20.  在 Q5 状态下，忽略所有 D，Z，向右移动。如果找到 C，使其从 Z 向左移动到状态 Q6。如果发现 B，忽略向左移动到状态 Q7
    21.  在 Q6 中，忽略所有 D，Z，向左移动。如果发现 Y，忽略它并向右移动到状态 Q4。
    22.  如果达到 Q7 状态，将产生接受字符串的结果。
    23.  在 Q8 中，忽略所有 A、Y、D，向左移动。如果发现 X，忽略它，向右移动到状态 Q9。如果发现 B，忽略它，向右移动到 Q11。
    24.  在 Q9 状态下，如果 A 找到了，让它向右移动到 Q10 状态
    25.  在 Q10 中，忽略所有 A，Y，向右移动。如果找到 D，将其变为 Y，并向右移动到状态 Q8。
    26.  如果达到 Q11 状态，将产生接受字符串的结果。