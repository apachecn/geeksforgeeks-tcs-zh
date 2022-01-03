# 如何识别一种语言是否有规律

> 原文:[https://www . geesforgeks . org/如何识别一种语言是否正规/](https://www.geeksforgeeks.org/how-to-identify-if-a-language-is-regular-or-not/)

先决条件–[正则表达式、正则语法和正则语言](https://www.geeksforgeeks.org/regular-expressions-regular-grammar-and-regular-languages/)、[泵引理](https://www.geeksforgeeks.org/theory-of-computation-pumping-lemma/)、
基于鸽子洞原理，有一个公认的定理可以识别一种语言是否是正则的，称为**泵引理**。但是抽引理是一个否定测试，即如果一种语言不满足抽引理，那么我们可以肯定地说它不是正则的，但是如果它满足，那么语言可能是正则的，也可能不是正则的。泵引理更多的是一种数学证明，需要更多的时间，有时可能会令人困惑。在考试中，我们需要非常快速地解决这个问题，因此根据常见的观察和分析，这里有一些快速的规则会有所帮助:

1.  Every finite set represents a regular language. 
    **Example 1 –** All strings of length = 2 over {a, b}* i.e. L = {aa, ab, ba, bb} is regular. 
2.  Given an expression of non-regular language, but the value of parameter is bounded by some constant, then the language is regular (means it has kind of finite comparison). 
    **Example 2 –** L = {![a^n   ](img/73a0695a1c427c01f28227aaa6c1cdb6.png "Rendered by QuickLaTeX.com")[Tex]b^n   [/Tex]| n <= 10<sup>1010</sup>} is regular, <u>because it is upper bounded and thus a finite language.</u> 
3.  The pattern of strings form an A.P.(Arithmetic Progression) is regular(i.e it’s power is in form of linear expression), 
    but the pattern with G.P.(Geometric Progression) is not regular(i.e its power is in form of non-linear expression) and it comes under class of Context Sensitive Language. 
    **Example 3 –** L = { ![a^n   ](img/73a0695a1c427c01f28227aaa6c1cdb6.png "Rendered by QuickLaTeX.com")| n>=2 } is regular. Clearly, it forms an A.P., so we can draw a finite automaton with 3 states. 

    **例 4–**l = { a<sup>2^n</sup>| n>= 1 }不规则。它形成了一个 G.P，所以我们不能有一个固定的模式，重复会产生这种语言的所有字符串。
    在示例 4 中，如果“n”像 n < 10000 一样有界，那么它就变得规则，因为它是有限的。

4.  No pattern is present, that could be repeated to generate all the strings in language is not regular.Finding prime itself is not possible with FA. 
    **Example 5 –** L = { ![a^p   ](img/919a043776990ae028b7b4a1ae9231a4.png "Rendered by QuickLaTeX.com")| p is prime. } is not regular. 
5.  A concatenation of pattern(regular) and a non-pattern(not regular) is also not a regular language. 
    **Example 6 –** L<sub>1</sub> = { ![a^{n}b^{n}   ](img/e6dfa2b1beba51f27df658b107f32d5d.png "Rendered by QuickLaTeX.com")| n≥1 }, L<sub>2</sub> = {![a^{n}   ](img/eb28349d48a305366e37ed466cf6df95.png "Rendered by QuickLaTeX.com")n≥1 } then L<sub>1</sub>.L<sub>2</sub> is not regular. 
6.  Whenever unbounded storage is required for storing the count and then comparison with other unbounded counts, then the language is not regular. 
    **Example 7 –** L = { ![a^n   ](img/73a0695a1c427c01f28227aaa6c1cdb6.png "Rendered by QuickLaTeX.com")[Tex]b^n   [/Tex]| n>=1 } is not regular, because we need to first store the count of a and then compare it against count of b, but finite automaton has a limited storage, but in L, there can be infinite number of a’s coming in, which can’t be stored. 

    **例 8–**L = { w | na(w)= nb(w)}不规则。

    **例 9–**L = { w | na(w)%3>nb(w)% 3 }是正则的，因为模运算需要有界存储，即模对于% 3 运算只能是 0、1 或 2，然后类似地对于 b，它将是 0、1 和 2。因此，在 DFA 中表示的状态将是 a 和 b 的余数的所有组合。

7.  **W，W<sup>r</sup>T3**x****y**的图案**
    *   If **|x|** is bounded to certain length, then not regular. 
        **Example 10 –** L = { W x W<sup>r</sup> | W, x belongs to{a, b}* and |x|=5 } is not regular. If W= abb then W<sup>r</sup> = bba and x = aab, so combined string is abb aab bba. Now, x can be expanded to eat away W and W<sup>r</sup> , but |x| = 5\. So, even in expanded string, W=ab, Wr=ba and x=baabb. So, we don’t get any pattern of form (a+b)*, so not regular. 
    *   If |x| is unbounded and W belongs to (a+b)*, then put W as epsilon and W^r as epsilon, if we get (a+b)* as a result then the language is regular. 
        **Example 11 –** L = { W x W<sup>r</sup> | W, x belongs to {a, b}* } is regular. 
        If W = abb then W<sup>r</sup> = bba and X = aab, so combined string is abb aab bba. Now, x can be expanded to eat away W and W<sup>r</sup> . So, in expanded string, W=epsilon,W<sup>r</sup> =epsilon and X=abb aab bba. We get simple pattern of form (a+b)* for which finite automaton can be drawn. 
    *   If |x| is unbounded and W belongs to (a+b)<sup>+</sup>, then put W as any symbol from alphabet and corresponding W<sup>r</sup> , if we can still get some combination of (a+b)* as a result, with a guarantee that all strings will be of the same form, then the language is regular else not regular. This needs more explanation with an example: 

        **例 12–**L = { W x W<sup>r</sup>| W，x 属于{a，b}+ }是正则的。
        如果 W = abb，那么 W <sup>r</sup> = bba，x = aab，那么组合字符串就是 abbaabbba。现在，X 可以展开吃掉 W 和 W <sup>r</sup> ，留下一个符号 a 或 b，在展开的字符串中，如果 W=a 那么 W <sup>r</sup> =a，如果 W=b 那么 W <sup>r</sup> =b，在上面的例子中，W <sup>r</sup> =a. x=bbaabbb。它简化为以相同符号 a(a+b)*a 或 b(a+b)*b 开始和结束的模式串，可以为其绘制有限自动机。

        **例 13–**L = { W W W<sup>r</sup>Y | W，Y 属于{0，1}+}不规则。
        如果 W= 101，那么 W <sup>r</sup> = 101，Y= 0111，那么字符串就是 1011010111。如果 y 展开，那么 W=1，W <sup>r</sup> =0，y=11010111。根据这种扩展，字符串不属于语言本身，这是错误的，因此不规则。

        如果 W= 110，那么 W <sup>r</sup> = 011，Y= 0111，那么字符串就是 1100110111。如果 Y 展开，那么 W=1，Wr=1，Y=00110111。这个字符串满足语言要求，但是我们不能以此为基础进行归纳，因为字符串也可能以 01 和 10 开头。

        **例 14–**L = { x WW<sup>r</sup>y | x，y，W 属于{a，b} <sup>+</sup> }是正则的。
        如果 X= aaaba，W=ab，Y=aab。字符串是 aaaba abbaaab。现在，X 和 y 可以被扩展，这样 W 和 W <sup>r</sup> 被吃掉，但是留下一个符号用于+即新值是 X= aaabaa W= b，W <sup>r</sup> = b。因此，语言被简化为包含“bb”或“aa”作为子字符串的所有字符串的集合，这是规则的。