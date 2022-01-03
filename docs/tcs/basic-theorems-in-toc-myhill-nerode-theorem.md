# TOC 中的基本定理(迈希尔内罗德定理)

> 原文:[https://www . geeksforgeeks . org/basic-定理-in-TOC-my hill-nerode-定理/](https://www.geeksforgeeks.org/basic-theorems-in-toc-myhill-nerode-theorem/)

迈希尔·内罗德定理是语言理论的一个基本结果。这个理论在 1958 年被**约翰·迈希尔**和**阿尼尔·内罗德**证明。它用于证明语言 L 是否是正则的，也用于确定性有限自动机中的状态最小化。

要理解这个定理，首先我们需要了解**不可区分性**是什么:

给定一种语言 l 和 x，y 是∑*上的字符串，如果对于每个字符串 z∑*，xz，yz ∈ L 或 xz，yz ∉ L，那么 x 和 y 在语言 l 上是不可区分的。

≦<sub>L</sub>是一个等价关系，因为它是:

1) **反身**:对于所有字符串 x，xz ∈ L iff xz ∈ L 因此 x≦<sub>L</sub>x。

2) **对称**:假设 x≦<sub>l</sub>y，这意味着 xz，yz ∈ L 或者 xz，yz ∉ L 对于所有 z∈∈*。等效地，这意味着 yz，xz ∈ L 或 yz，xz ∉ L 适用于所有 z∈∈*这意味着 y≦<sub>l</sub>x

3) **传递**:假设 x≦<sub>L</sub>y 和 y≦<sub>L</sub>w，那么为了矛盾假设 x 和 w 不是不可区分的。这意味着必须存在某个 z，这样 xz 和 wz 中正好有一个是 l 的成员。假设 xz 是 l 的成员，wz 不是 l 的成员。xz ∈ L 意味着 yz∈l。wz∉l 意味着 yz ∉ L。这是一个矛盾，因为 yz 不能既是 l 的成员又不是 l 的成员。因此 x≦<sub>l</sub>y 和 y≦<sub>l</sub>w

由于≦<sub>L</sub>是∑*上的等价关系，≦<sub>L</sub>将∑*划分为不相交的集合，称为**等价类。**

**迈希尔内罗德定理:**

一种语言是正则的当且仅当≦<sub>L</sub>将∑*划分为有限多个等价类。如果≦<sub>L</sub>将∑*划分为 **n** 等价类，那么识别 L 的最小 DFA 恰好具有 **n** 状态。

示例:

**证明 L = {a <sup>n</sup> b <sup>n</sup> | n ≥ 0}不规则。**

我们可以证明 L 有无限多的等价类，只要 k ≠ i，a <sup>k</sup> 和 a <sup>i</sup> 就可以用 L 来区分。因此，对于 x = a <sup>k</sup> 和 y = a <sup>i</sup> ，我们让 z = b <sup>k</sup> 。那么 xz = a <sup>k</sup> b <sup>k</sup> 在语言中，但是 yz = a <sup>i</sup> b <sup>k</sup> 不在语言中。因此，L 的每个等价类最多可以包含一个形式为 a <sup>i</sup> 的字符串，所以等价类一定是无限多的。这意味着根据迈希尔内罗德定理，L 不是正则的。

注:证明语言 L 是否正则也是用泵引理完成的，这和迈希尔内罗德定理的区别是，有一些非正则语言满足泵引理，但没有这样的非正则语言满足迈希尔内罗德定理。