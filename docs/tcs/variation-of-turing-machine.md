# 图灵机的变异

> 原文:[https://www.geeksforgeeks.org/variation-of-turing-machine/](https://www.geeksforgeeks.org/variation-of-turing-machine/)

先决条件–[图灵机](https://www.geeksforgeeks.org/turing-machine/)

**1。多磁道图灵机:**

*   A k-tack Turing machine (for some k > 0) has k tracks and a read-write head, which can read and write all tracks one by one.
*   A K-track Turing machine can use a single-track Turing machine.

来模拟

**2。双向无限带图灵机:**

*   The infinite belt of the bidirectional Turing machine is unbounded in both left and right directions.
*   Two-way infinite Turing Machine can be simulated by one-way infinite Turing Machine (standard Turing Machine).

**3。多带图灵机:**

*   它有多个磁带，由一个磁头控制。
*   多带图灵机不同于 k 轨迹图灵机，但表现力是一样的。
*   多带图灵机可以用单带图灵机来模拟。

**4。多带多头图灵机:**

*   How many multi-belt Turing machines have multi-belts?
*   Each belt is controlled by a separate head.
*   Turing machines with multiple heads can be simulated by standard Turing machines.

**5。多维磁带图灵机:**

*   It has a multi-dimensional tape, and the magnetic head can move left, right, up or down in any direction.
*   Multi-dimensional Turing machine can be used by one-dimensional Turing machine.

进行模拟

**6。多头图灵机:**

*   A multi-head Turing machine contains two or more heads to read symbols on the same tape.
*   In one step, all heads perceive the scanned symbols and move or write independently.
*   Multi-head Turing machine can be simulated by single-head Turing machine.

**7。非确定性图灵机:**

*   Non-deterministic Turing machines have a single, unidirectional infinite tape.
*   For a given state and input symbol, at least one option can be moved (the number of options to be moved next time is limited), and each option has several path options that a given input string may follow.
*   Non-deterministic Turing Machine is equivalent to deterministic Turing Machine.