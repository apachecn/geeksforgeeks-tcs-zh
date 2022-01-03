# 将上下文无关语法转换为 Greibach 范式

> 原文:[https://www . geesforgeks . org/converting-context-free-grammar-grei Bach-normal-form/](https://www.geeksforgeeks.org/converting-context-free-grammar-greibach-normal-form/)

先决条件–[上下文无关语法](https://www.geeksforgeeks.org/classification-of-context-free-grammars/)、[简化上下文无关语法](https://www.geeksforgeeks.org/simplifying-context-free-grammars/)

如果所有生成规则满足以下条件之一，则上下文无关语法(CGF)处于格雷巴赫范式(GNF)中:

*   生成终端的非终端(例如；X->x)
*   一个非终端生成一个终端，后跟任意数量的非终端(例如；X->xX1X2…Xn)
*   开始生成符号ε。(例如；S-> ε)

考虑以下语法:

```
G1 = {S->aA|bB, B->bB|b, A->aA|a} 
G2 = {S->aA|bB, B->bB|ε, A->aA|ε}
```

G1 的语法在 GNF，因为生产规则满足为 GNF 指定的规则。但是，语法 G2 不在 GNF，因为生产规则 B-> ε和 A-> ε不满足为 GNF 指定的规则(只有开始符号才能生成ε)。
**注–**

*   对于给定的语法，可以有多个 GNF
*   GNF 生产与 CFG 生成的语言相同的语言

**如何将 CFG 转换为 GNF–**

**第一步。**把语法转换成 CNF。
如果给定的语法不在 CNF，将其转换为 CNF。您可以参考以下文章将 CFG 转换为 CNF: [将上下文无关语法转换为乔姆斯基范式](https://www.geeksforgeeks.org/converting-context-free-grammar-chomsky-normal-form/)

**第二步。**如果存在左递归，则从语法中消除它。
如果 CFG 包含左递归，消除它们。你可以参考以下文章来消除左递归:[解析|集合 1(介绍、歧义和解析器)](https://www.geeksforgeeks.org/parsing-set-1-introduction-ambiguity-and-parsers/)

**第三步。**将生产规则转换为 GNF 形式。
如果任何生产规则不是 GNF 形式，转换它们。让我们举个例子，把 CFG 转换成 GNF。考虑给定的语法 G1:

```
S → XA|BB 
B → b|SB 
X → b 
A → a
```

由于 G1 已经在 CNF，并且没有左递归，我们可以跳过第 1 步和第 2 步，直接进入第 3 步。
生产规则 B- > SB 不在 GNF，因此，我们将生产规则 B- > SB 中的 S - > XA|BB 替换为:

```
S → XA|BB 
B → b|XAB|BBB 
X → b 
A → a
```

生产规则 S->XA 和 B->XAB 不在 GNF，因此，我们将生产规则 S->XA 和 B->XAB 中的 X->b 替换为:

```
S → bA|BB 
B → b|bAB|BBB 
X → b 
A → a
```

去掉左递归(B->BBB)，我们得到:

```
S → bA|BB 
B → bC|bABC
C → BBC| ε
X → b 
A → a
```

除去零生产(C-> ε)，我们得到:

```
S → bA|BB 
B → bC|bABC|b|bAB
C → BBC|BB
X → b 
A → a
```

生产规则 S->BB 不在 GNF，因此，我们将生产规则 S->BB 中的 B → bC|bABC|b|bAB 替换为:

```
S → bA| bCB|bABCB|bB|bABB 
B → bC|bABC|b|bAB
C → BBC|BB
X → b 
A → a
```

生产规则 C->BB 不在 GNF，因此，我们将生产规则 C->BB 中的 B → bC|bABC|b|bAB 替换为:

```
S → bA| bCB|bABCB|bB|bABB 
B → bC|bABC|b|bAB
C → BBC
C → bCB|bABCB|bB|bABB
X → b 
A → a
```

制作规则 C->BBC 不在 GNF，因此，我们将制作规则 C->BBC 中的 B → bC|bABC|b|bAB 替换为:

```
S → bA| bCB|bABCB|bB|bABB 
B → bC|bABC|b|bAB
C → bCBC|bABCBC|bBC|bABBC
C → bCB|bABCB|bB|bABB
X → b 
A → a
```

这是 G1 语法的 GNF 形式。