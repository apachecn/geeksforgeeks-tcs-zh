# 实数系公理

> 原文:[https://www.geeksforgeeks.org/axioms-of-real-number-system/](https://www.geeksforgeeks.org/axioms-of-real-number-system/)

在这篇文章中，我们将了解一些关于**实分析**的非常基本的思想，即实数系统结构的研究。我们将讨论被认为由实数集![R](img/ba4e2d8bd8b5b3f5b8c3d335494a5e65.png "Rendered by QuickLaTeX.com")满足的三个公理

这三个公理是:

1.  领域公理
2.  顺序公理
3.  完备性公理

**域公理**:集合![R   ](img/03ade79b5904c4588969685c6effa51b.png "Rendered by QuickLaTeX.com")表示为域![(R, +, .)    ](img/522dcfd0bd559c0bdc4d11fb8849e225.png "Rendered by QuickLaTeX.com")，其中![+   ](img/c0112d5f9915ea4d97ca3e34f9a10e1e.png "Rendered by QuickLaTeX.com")和![.   ](img/1302a351ba2053d25a6b6c5ec4044d97.png "Rendered by QuickLaTeX.com")分别是加法和乘法的二元运算。它由 4 个加法和乘法公理和一个分配律组成。

**(i)** 加法公理:

*   ![a+b = b+a \ ∀ \ a,b \ ∈ R](img/ab13c1b653406eafe34b64c1faf0e185.png "Rendered by QuickLaTeX.com")
*   ![(a+b)+c = a+(b+c) \ ∀ \ a,b,c \ ∈ R](img/33db17eb2caca1df8133ec008e5202d4.png "Rendered by QuickLaTeX.com")
*   r 包含元素 0，因此![a + 0 = a \ ∀ \ a ∈ R ](img/f179f73201144ae11debe8578357fee0.png "Rendered by QuickLaTeX.com")
*   每个![a ∈ R   ](img/3f5f88c7d8ec19438e1c3a3bd7bef8be.png "Rendered by QuickLaTeX.com")对应一个元素![-a ∈ R   ](img/333a718596b21b7b6885dde57b0e52fd.png "Rendered by QuickLaTeX.com")，这样![a+(-a) = 0](img/15c62fc715fa68fabfb1c752f0b907c5.png "Rendered by QuickLaTeX.com")

**(二)**乘法公理:

*   ![ab = ba \ ∀\ a,b  ∈ R](img/c4b986d287aadfc852bbd3e0e206ac26.png "Rendered by QuickLaTeX.com")
*   ![(ab)c = a(bc) \ ∀ \ a,b,c  ∈ R](img/9b9ebaaac6880d82babcfe3fcb52f4e1.png "Rendered by QuickLaTeX.com")
*   ![R   ](img/03ade79b5904c4588969685c6effa51b.png "Rendered by QuickLaTeX.com")包含一个元素![1   ](img/1945db1d173052ae2cca990f110560aa.png "Rendered by QuickLaTeX.com")，使得![ 1.a = a \ ∀ \ a ∈ R   ](img/1c7162d1278846f3876577d1be5d6b76.png "Rendered by QuickLaTeX.com")和![ 1 ≠ 0](img/90da91731aae7a0d5e0c6894ea317d79.png "Rendered by QuickLaTeX.com")
*   如果![a ∈ R \ and \ a≠0   ](img/51227b18d4fefe2ffa31c4039bd3f9f4.png "Rendered by QuickLaTeX.com")存在一个元素![\frac{1}{a} ∈ R   ](img/47181e4bfda097e8adc45e3c57d7b6c2.png "Rendered by QuickLaTeX.com")，这样![a. (\frac{1}{a} ) = 1](img/9a0abc492b91c6ba749249afd990944b.png "Rendered by QuickLaTeX.com")

**(三)**分配规律:

*   ![a(b+c) = ab+ac \ ∀ \ a,b,c ∈ R](img/0363ecd792babf7bf94832ec4c9c2d34.png "Rendered by QuickLaTeX.com")

**序公理**:我们定义![>   ](img/f98d92072e103a51ac57f6dab834cf1f.png "Rendered by QuickLaTeX.com")(大于)为序关系，满足以下公理–

*   三分法——对于![a,b∈ R   ](img/65a1fe19f1589ca1c0220f50cb2cba30.png "Rendered by QuickLaTeX.com")来说，只有一个表达式是正确的:![a>b , a=b , b>a](img/2a07d8c33dd3edd946d81d0f52427813.png "Rendered by QuickLaTeX.com")
*   传递性–对于![a,b,c∈R \ a>b,\ b>c ⇒ a>c](img/1261a3f638659768cf182dc9d6cdbd50.png "Rendered by QuickLaTeX.com")
*   加法的单调性质–用于![a,b,c∈R, \ a>b ⇒ a+c > b+c ](img/c7a46855493b26b3ee83b935f0184c35.png "Rendered by QuickLaTeX.com")
*   乘法的单调性质–用于![a,b,c∈R,\ a>b, c>0 ⇒ ac > bc](img/a81b9835042b46cc0c75ac93ae07c783.png "Rendered by QuickLaTeX.com")

我们称![>   ](img/f98d92072e103a51ac57f6dab834cf1f.png "Rendered by QuickLaTeX.com")为线性序，![R   ](img/03ade79b5904c4588969685c6effa51b.png "Rendered by QuickLaTeX.com")为**线性序场**。

在定义完备性公理之前，我们先来看看有界性的概念。在这里，我们将在陈述完备性公理之前定义几个术语。

**集合**:任何非空子集，比如![A  ](img/d87f1cb8a8e09ef6d976b963803548e2.png "Rendered by QuickLaTeX.com")，在![R  ](img/de6ee272267f4ab1e72d49bdeb53f21b.png "Rendered by QuickLaTeX.com")中被称为**集合**。例如，集合![Z^+  ](img/f497f0169e6c08bd93179d89be26fdb5.png "Rendered by QuickLaTeX.com")是一个集合。类似地，集合 B = {1，2，4，8}也是一个集合，因为![B ⊆ R  ](img/fe304d5a23232af3a97bd3561503d199.png "Rendered by QuickLaTeX.com")但是，集合 A = {x，y，z}和空集合![∅  ](img/7c4f32c0a3b4724709dc38b95960b830.png "Rendered by QuickLaTeX.com")不是集合。

**上限**:如果![∃ \ k_1\ ∈ R  ](img/314bead85b9758dfa00c60a59ad0b708.png "Rendered by QuickLaTeX.com")是![x ∈ S ⇒ x \leq k_1  ](img/1a933680f3af4b87a52d8ce99220588d.png "Rendered by QuickLaTeX.com")，则![R  ](img/de6ee272267f4ab1e72d49bdeb53f21b.png "Rendered by QuickLaTeX.com")的子集![S  ](img/286065faa2e31cda66548efbe78a36d1.png "Rendered by QuickLaTeX.com")被称为**在**之上。这个数字![k_1  ](img/ae7dc471a5d1a0f7dca298f464df6a41.png "Rendered by QuickLaTeX.com")叫做![S  ](img/286065faa2e31cda66548efbe78a36d1.png "Rendered by QuickLaTeX.com")的一个**上限**。比如负实数的集合![R^-  ](img/1009789d9ade3e1d0090aaef8fcddbf5.png "Rendered by QuickLaTeX.com")是上界的，![0  ](img/1957d0c119c059733abddeb117432e40.png "Rendered by QuickLaTeX.com")是上界的。同样，负整数的集合![Z^-  ](img/3792876d80812636bb260189a73ec68b.png "Rendered by QuickLaTeX.com")在上界，![-1  ](img/02c363e776ac94cb3cb392806b7abe90.png "Rendered by QuickLaTeX.com")为上界。但是，正实数的集合![R^+  ](img/9406244397bbc2842883b526cd1fe46b.png "Rendered by QuickLaTeX.com")在上面是没有边界的。

**下界**:如果![∃ \ k_2\ ∈ R  ](img/30978d9baf7e6a8af2e459661b5b6af7.png "Rendered by QuickLaTeX.com")这样的![x ∈ S ⇒ x \geq k_2  ](img/ece113381f63571839a3346ffbaad8d8.png "Rendered by QuickLaTeX.com")这个数![k_2  ](img/3dbc5e4226d13defe662a0d81b407214.png "Rendered by QuickLaTeX.com")叫做 s 的**下界**，那么![R  ](img/de6ee272267f4ab1e72d49bdeb53f21b.png "Rendered by QuickLaTeX.com")的子集![S  ](img/286065faa2e31cda66548efbe78a36d1.png "Rendered by QuickLaTeX.com")就称之为有界于下，比如集合![R^+  ](img/9406244397bbc2842883b526cd1fe46b.png "Rendered by QuickLaTeX.com")有界于下，![0  ](img/1957d0c119c059733abddeb117432e40.png "Rendered by QuickLaTeX.com")就是下界。同样的，集合![Z^+  ](img/f497f0169e6c08bd93179d89be26fdb5.png "Rendered by QuickLaTeX.com")是下界，![1  ](img/2a68dc4b37180a096b26d1b1d3429eef.png "Rendered by QuickLaTeX.com")是上界。但是，设定![R^-  ](img/1009789d9ade3e1d0090aaef8fcddbf5.png "Rendered by QuickLaTeX.com")并不局限于此。

**最小上界**:考虑一个集合![S  ](img/286065faa2e31cda66548efbe78a36d1.png "Rendered by QuickLaTeX.com")的上界![u  ](img/2ed67cc6e8698a7ae93531d7c5807a35.png "Rendered by QuickLaTeX.com")，任何小于![u  ](img/2ed67cc6e8698a7ae93531d7c5807a35.png "Rendered by QuickLaTeX.com")的实数都不是![S  ](img/286065faa2e31cda66548efbe78a36d1.png "Rendered by QuickLaTeX.com")的上界，那么我们说![u  ](img/2ed67cc6e8698a7ae93531d7c5807a35.png "Rendered by QuickLaTeX.com")就是![S.](img/6ae3dea74843b58f8db92dfb6ce773da.png "Rendered by QuickLaTeX.com")的**最小上界(lub)** 或者**上界(sup)**

**最大下界**:考虑一个集合![S  ](img/286065faa2e31cda66548efbe78a36d1.png "Rendered by QuickLaTeX.com")的下界![v  ](img/697540b8c5e9b65dfb5b54a1e6099d99.png "Rendered by QuickLaTeX.com")，任何大于![v  ](img/697540b8c5e9b65dfb5b54a1e6099d99.png "Rendered by QuickLaTeX.com")的实数都不是![S  ](img/286065faa2e31cda66548efbe78a36d1.png "Rendered by QuickLaTeX.com")的下界，那么我们说![v  ](img/697540b8c5e9b65dfb5b54a1e6099d99.png "Rendered by QuickLaTeX.com")就是![S.](img/6ae3dea74843b58f8db92dfb6ce773da.png "Rendered by QuickLaTeX.com")的**最大下界(glb)或者下确界(inf)**

<u>例</u>:让![S = [0,1]  ](img/7fecb338007a8387399f3f0651111d46.png "Rendered by QuickLaTeX.com")。对于 S，我们看到 1 是上界，任何小于 1 的数都不是 S 的上界，因此，1 是 S 的上确界。此外，0 是下界，任何大于 0 的数都不是下界，因此，0 是 S 的下确界

**有界性**:如果一个集合 S 既是上有界的又是下有界的，那么它就是有界的。也就是说，它必须既有上限又有下限。例如，任何有限集合都是有界的，空集合![∅  ](img/7c4f32c0a3b4724709dc38b95960b830.png "Rendered by QuickLaTeX.com")也是有界的。但是![Q  ](img/90ee5264169bf40d0158ac58a1ecae74.png "Rendered by QuickLaTeX.com")和![R  ](img/de6ee272267f4ab1e72d49bdeb53f21b.png "Rendered by QuickLaTeX.com")的集合是没有界限的。

**注**:一个集合不需要有一个最大成员和一个最小成员分别在上面有界或在下面有界。

现在完成了所需的定义，我们声明**完备性公理(也称为最小上限公理)**。

**“上面有界的每个非空实数集都有一个上确界。”**

集合 R 满足**场公理**、**序公理**和**完备性公理**。因此实数集合![R  ](img/de6ee272267f4ab1e72d49bdeb53f21b.png "Rendered by QuickLaTeX.com")被称为**完全有序域。**

同样，有理数集合![Q  ](img/90ee5264169bf40d0158ac58a1ecae74.png "Rendered by QuickLaTeX.com")不满足完备性公理。因此，![Q  ](img/90ee5264169bf40d0158ac58a1ecae74.png "Rendered by QuickLaTeX.com")不是一个完整的字段。

完备性公理是实数系的一个非常基本和重要的性质，作为各种微积分定理、极大极小概念、中值定理等的证明。依靠实数的完备性。