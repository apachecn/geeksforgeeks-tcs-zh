# 将上下文无关语法转换为乔姆斯基范式

> 原文:[https://www . geesforgeks . org/converting-context-free-grammar-Chomsky-normal-form/](https://www.geeksforgeeks.org/converting-context-free-grammar-chomsky-normal-form/)

先决条件–[简化上下文无关语法](https://www.geeksforgeeks.org/simplifying-context-free-grammars/)

如果所有生成规则满足以下条件之一，则上下文无关语法(CFG)处于乔姆斯基范式(CNF)中:

*   生成终端的非终端(例如；X->x)
*   产生两个非终端的非终端(例如；X->YZ)
*   开始生成符号ε。(例如；S-> ε)

考虑以下语法，

```
G1 = {S->a, S->AZ, A->a, Z->z} 
G2 = {S->a, S->aZ, Z->a}

```

G1 的语法在 CNF，因为生产规则满足为 CNF 指定的规则。但是，语法 G2 不在 CNF，因为生产规则 S->aZ 包含后面跟非终端的终端，不满足为 CNF 指定的规则。

**注–**

*   对于给定的语法，可以有多个 CNF。
*   CNF 生产与 CFG 生成的语言相同的语言。
*   CNF 被用作许多 CFG 算法的预处理步骤，如 CYK 算法(隶属算法)、自底向上解析器等。
*   为了生成长度为“n”的字符串 w，需要在 CNF 进行“2n-1”的生产或步骤。
*   任何语言中没有ε的上下文无关文法都有一个等价的 CNF。

**如何将 CFG 转换成 CNF？**

**第一步。**从 RHS 中消除开始符号。
如果开始符号 S 位于语法中任何产品的 RHS 处，则创建一个新的产品为:
S0- > S
，其中 S0 是新的开始符号。

**第二步。**消除无效、单位和无用的生产。
如果 CFG 包含无效、单位或无用的生产规则，则将其消除。你可以参考[这篇文章来消除这些类型的生产规则](https://www.geeksforgeeks.org/simplifying-context-free-grammars/)。

**第三步。**如果端子与其他端子或非端子一起存在，则从 RHS 中删除端子。例如，；生产规则 X- > xY 可以分解为:
X- > ZY
Z- > x

**第四步。**消除两个以上非端子的 RHS。
例如；生产规则 X- > XYZ 可以分解为:
X- > PZ
P- > XY

**示例–**我们举个例子，把 CFG 转换成 CNF。考虑给定的语法 G1:

```
S → ASB
A → aAS|a|ε 
B → SbS|A|bb

```

**第一步。**当开始符号 S 出现在 RHS 上时，我们将创建一个新的生产规则 S0- > S。因此，语法将变成:

```
S0->S
S → ASB
A → aAS|a|ε 
B → SbS|A|bb

```

**第二步。**由于语法包含空生产 A- > ε，将其从语法中移除会产生:

```
S0->S
S → ASB|SB
A → aAS|aS|a 
B → SbS| A|ε|bb

```

现在，它创建了零生产 B→ ε，将其从语法中移除会产生:

```
S0->S
S → AS|ASB| SB| S
A → aAS|aS|a 
B → SbS| A|bb

```

现在，它创建了单位生产 B->A，将其从语法中移除会产生:

```
S0->S
S → AS|ASB| SB| S
A → aAS|aS|a 
B → SbS|bb|aAS|aS|a

```

此外，从语法中删除单位生产 S0->S 会产生:

```
S0-> AS|ASB| SB| S
S → AS|ASB| SB| S
A → aAS|aS|a 
B → SbS|bb|aAS|aS|a

```

此外，从语法中删除单位生产 S->S 和 S0->S 会产生:

```
S0-> AS|ASB| SB
S → AS|ASB| SB
A → aAS|aS|a 
B → SbS|bb|aAS|aS|a

```

**第三步。**在生产规则 A- > aAS |aS 和 B- > SbS|aAS|aS 中，端子 A 和 B 存在于 RHS 上，且未终止。将它们从 RHS 中移除:

```
S0-> AS|ASB| SB
S → AS|ASB| SB
A → XAS|XS|a
B → SYS|bb|XAS|XS|a
X →a
Y→b

```

此外，B->bb 不能成为 CNF 的一部分，将其从语法中删除会产生:

```
S0-> AS|ASB| SB
S → AS|ASB| SB
A → XAS|XS|a
B → SYS|VV|XAS|XS|a
X → a
Y → b
V → b

```

**第 4 步:**在产生式规则 S0- > ASB 中，RHS 有两个以上的符号，将其从语法中移除会产生:

```
S0-> AS|PB| SB
S → AS|ASB| SB
A → XAS|XS|a
B → SYS|VV|XAS|XS|a
X → a
Y → b
V → b
P → AS

```

同样，S->ASB 有两个以上的符号，将其从语法中删除会产生:

```
S0-> AS|PB| SB
S → AS|QB| SB
A → XAS|XS|a
B → SYS|VV|XAS|XS|a
X → a
Y → b
V → b
P → AS
Q → AS

```

类似地，A->XAS 有两个以上的符号，从语法中去掉它会产生:

```
S0-> AS|PB| SB
S → AS|QB| SB
A → RS|XS|a
B → SYS|VV|XAS|XS|a
X → a
Y → b
V → b
P → AS
Q → AS
R → XA

```

类似地，B->SYS 有两个以上的符号，将其从语法中删除会产生:

```
S0 -> AS|PB| SB
S → AS|QB| SB
A → RS|XS|a
B → TS|VV|XAS|XS|a
X → a
Y → b
V → b
P → AS
Q → AS
R → XA
T → SY

```

同样，B->XAX 有两个以上的符号，把它从语法中去掉会产生:

```
S0-> AS|PB| SB
S → AS|QB| SB
A → RS|XS|a
B → TS|VV|US|XS|a
X → a
Y → b
V → b
P → AS
Q → AS
R → XA
T → SY
U → XA

```

这是给定语法所需的 CNF。