# 数学|环同态

> 原文:[https://www . geesforgeks . org/mathematics-ring-同态/](https://www.geeksforgeeks.org/mathematics-ring-homomorphisms/)

**先决条件:**T2 戒指

**环同态:**
对集合![R  ](img/de6ee272267f4ab1e72d49bdeb53f21b.png "Rendered by QuickLaTeX.com")进行任意两次二元运算的集合![R  ](img/de6ee272267f4ab1e72d49bdeb53f21b.png "Rendered by QuickLaTeX.com")由![+  ](img/47acf37fe84c4cb27fc7a8b69add4080.png "Rendered by QuickLaTeX.com")和![*  ](img/be26e44678acf2bb11973116ce167966.png "Rendered by QuickLaTeX.com")表示的 let 称为表示为![(R, +, *)  ](img/32f4b14756416f69ec43835dac63c7ec.png "Rendered by QuickLaTeX.com")的环，如果![(R, +)  ](img/ef65cf53616127a08426993948a3d041.png "Rendered by QuickLaTeX.com")是阿贝尔群，![(R, *)  ](img/31008bf3662ee16c6e369cb8d6bf41bc.png "Rendered by QuickLaTeX.com")是半群，它们也遵循左右分配律。

对于两个环![(R,+,*)  ](img/2eb3fd8b664700a604509a297f8f2ff1.png "Rendered by QuickLaTeX.com")和![(S,⨁,  ](img/9c5f94435e30b1707d8818ffbfa9dd8b.png "Rendered by QuickLaTeX.com")【Tex】\次[/Tex] ![)  ](img/b01c1fbe5e28b231c9ef2bbb7f3b977d.png "Rendered by QuickLaTeX.com")来说，映射![f : R → S  ](img/163f06574e0bc30836ebf79367359555.png "Rendered by QuickLaTeX.com")被称为环同态，如果

1.  ![f (a + b) = f (a) ⨁ f (b)  ](img/02564f82e069226b36230adf1f1c3498.png "Rendered by QuickLaTeX.com")、∀a、b∑![R  ](img/de6ee272267f4ab1e72d49bdeb53f21b.png "Rendered by QuickLaTeX.com")。
2.  ![f(a * b) = f(a) \times  f(b)  ](img/a1baa568973bc249dc0312e18206a948.png "Rendered by QuickLaTeX.com")、∀a、b∑![R  ](img/de6ee272267f4ab1e72d49bdeb53f21b.png "Rendered by QuickLaTeX.com")。
3.  ![f  ](img/857baa8880e9b15bc29cbf4a3b4da7cb.png "Rendered by QuickLaTeX.com")【Tex】([/Tex]I<sub>R</sub>![)  ](img/b01c1fbe5e28b231c9ef2bbb7f3b977d.png "Rendered by QuickLaTeX.com")![=  ](img/4547cccbd06f0911bf9e1159872f6566.png "Rendered by QuickLaTeX.com")I<sub>S</sub>，如果 I <sub>R</sub> 和 I <sub>S</sub> 分别是集![R  ](img/de6ee272267f4ab1e72d49bdeb53f21b.png "Rendered by QuickLaTeX.com")于![*  ](img/be26e44678acf2bb11973116ce167966.png "Rendered by QuickLaTeX.com")和集![S  ](img/286065faa2e31cda66548efbe78a36d1.png "Rendered by QuickLaTeX.com")于![\times   ](img/ac1601c0d0ba514ba603d049bcb9ea30.png "Rendered by QuickLaTeX.com")操作的身份(如果存在的话)。

注:*环* ![(S,⨁, \times )  ](img/753ff9fbd126101b99c37f75a485ab94.png "Rendered by QuickLaTeX.com") *称为环* ![(R,+,*)  ](img/2eb3fd8b664700a604509a297f8f2ff1.png "Rendered by QuickLaTeX.com") *的同形像。*

**示例:**

1.  函数 f(x) = x mod(n)从组(![Z  ](img/3c007a16aafc5743d1909df0180292a2.png "Rendered by QuickLaTeX.com")，+，*)到(![Z  ](img/3c007a16aafc5743d1909df0180292a2.png "Rendered by QuickLaTeX.com") <sub>n</sub> ，+，*)∀x∑![Z, Z  ](img/d9f075245601eb11ab9e0f7a96740dea.png "Rendered by QuickLaTeX.com")是一组整数。+和*分别是简单的加法和乘法运算。
2.  对于任意两个群(r，+，*)和(S,⨁，![\times  ](img/8f7b158182986e06d13f81cdc002dd0f.png "Rendered by QuickLaTeX.com") ) ∀x ∈ R，函数 f(x) = x，称为同态环同态。
3.  对于∀x ∈ N，函数 f(x) = 0。
4.  函数 f(x) =它本身是复共轭形式群(C，+，*)，这里 C 是复数的集合。+和*分别是简单的加法和乘法运算。

**注:** *如果 f 是来自(r，+，*)和(S,⨁，* ![\times  ](img/8f7b158182986e06d13f81cdc002dd0f.png "Rendered by QuickLaTeX.com") *的同态，那么 f(O <sub> R </sub> ) = f(O <sub>S</sub> )，其中 O <sub>R</sub> 和 O <sub>S</sub> 分别是集合 R over +和集合 S over ⨁运算的恒等式。*

**注:** *如果 f 是来自(r，+，*)和(S,⨁，* ![\times  ](img/8f7b158182986e06d13f81cdc002dd0f.png "Rendered by QuickLaTeX.com") *)的环同态，那么 f : (R，+) → (S,⨁)就是群同态。*

**环同构:**
从环![R  ](img/de6ee272267f4ab1e72d49bdeb53f21b.png "Rendered by QuickLaTeX.com")到环![S  ](img/286065faa2e31cda66548efbe78a36d1.png "Rendered by QuickLaTeX.com")的一一并到同态称为环同构，![R   ](img/03ade79b5904c4588969685c6effa51b.png "Rendered by QuickLaTeX.com")和![S  ](img/286065faa2e31cda66548efbe78a36d1.png "Rendered by QuickLaTeX.com")是同构的。

**环自同构:**
从环到自身的同态称为环自同构。

**场同态:**
对于两个场![(F,+,*)  ](img/2d896dffdcd687c923c807c4b66bab39.png "Rendered by QuickLaTeX.com")和![(K,⨁, \times)  ](img/496c66bf4af9a62d1b7be731c7a07f9c.png "Rendered by QuickLaTeX.com")一个映射![f : F → K   ](img/0b4af520968ed6422c8ebc44b7ea4f2e.png "Rendered by QuickLaTeX.com")被称为场同态，如果

1.  ![f(a + b) = f(a) ⨁ f(b)  ](img/30a9832d9e3494ad2758a5fac75eeb54.png "Rendered by QuickLaTeX.com")、∀a、b∑![F  ](img/f53bbacaaeb4bcb079316d0d72d18e29.png "Rendered by QuickLaTeX.com")。
2.  ![f(a * b) = f(a)  \times  f(b)  ](img/cefac53178096b0dc4c71dc27db175e6.png "Rendered by QuickLaTeX.com")、∀a、b∑![F  ](img/f53bbacaaeb4bcb079316d0d72d18e29.png "Rendered by QuickLaTeX.com")。
3.  ![f(  ](img/7baeda3767ce3036c9b8bcfc0768595f.png "Rendered by QuickLaTeX.com") I <sub> F </sub> ![)  ](img/b01c1fbe5e28b231c9ef2bbb7f3b977d.png "Rendered by QuickLaTeX.com") ![=  ](img/4547cccbd06f0911bf9e1159872f6566.png "Rendered by QuickLaTeX.com") I <sub>K</sub> ，其中 I <sub>F</sub> 和 I <sub>K</sub> 分别是设置![F   ](img/39ce09c1bfa648f5c26a2c014aaeae66.png "Rendered by QuickLaTeX.com")于![*   ](img/4ccaa53932b44a1d05ed8f789703d0fc.png "Rendered by QuickLaTeX.com")和设置![K  ](img/aa076c3d3015a34419fb7cfa4831a2ac.png "Rendered by QuickLaTeX.com")于![\times  ](img/8f7b158182986e06d13f81cdc002dd0f.png "Rendered by QuickLaTeX.com")操作的身份。
4.  ![f(  ](img/7baeda3767ce3036c9b8bcfc0768595f.png "Rendered by QuickLaTeX.com") O <sub> F </sub> ![)  ](img/b01c1fbe5e28b231c9ef2bbb7f3b977d.png "Rendered by QuickLaTeX.com") ![=  ](img/4547cccbd06f0911bf9e1159872f6566.png "Rendered by QuickLaTeX.com") O <sub>K</sub> ，其中 O <sub>F</sub> 和 O <sub>K</sub> 分别是设置![F  ](img/f53bbacaaeb4bcb079316d0d72d18e29.png "Rendered by QuickLaTeX.com")于![+  ](img/47acf37fe84c4cb27fc7a8b69add4080.png "Rendered by QuickLaTeX.com")和设置![K  ](img/aa076c3d3015a34419fb7cfa4831a2ac.png "Rendered by QuickLaTeX.com")于![⨁  ](img/a2977dde86bcc02dd6f91e92c41b766c.png "Rendered by QuickLaTeX.com")操作的标识。