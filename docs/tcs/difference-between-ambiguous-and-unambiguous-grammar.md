# 歧义语法和非歧义语法的区别

> 原文:[https://www . geeksforgeeks . org/歧义和非歧义语法之间的区别/](https://www.geeksforgeeks.org/difference-between-ambiguous-and-unambiguous-grammar/)

先决条件–[上下文无关语法](https://www.geeksforgeeks.org/classification-of-context-free-grammars/)
**1。[歧义语法](https://www.geeksforgeeks.org/ambiguous-grammar/) :**
如果存在多个派生树或解析树，则上下文无关语法称为歧义语法。

**示例–**

```
S -> S + S / S * S / S / a 
```

**2。明确语法:**
如果存在且仅有一个派生树或解析树，则上下文无关语法称为明确语法。

**示例–**

```
X -> AB
A -> Aa / a
B -> b 
```

**歧义和不歧义语法的区别:**

<center>

| S.NO | 模糊语法 | 无歧义文法 |
| --- | --- | --- |
| 1. | 在模棱两可的语法中，最左边和最右边的派生词是不一样的。 | 在明确的语法中，最左边和最右边的派生是相同的。 |
| 2. | 歧义语法中的非终结点数量少于无歧义语法。 | 无歧义语法中的非终结点数量多于有歧义语法中的非终结点数量。 |
| 3. | 歧义语法中的解析树长度相对较短。 | 明确语法中解析树的长度相对较大。 |
| 4. | 歧义语法中树的推导速度比无歧义语法快。 | 无歧义语法中的树的推导速度比有歧义语法慢。 |
| 5. | 不明确的语法会生成多个分析树。 | 明确的语法只生成一个解析树。 |
| 6. | 歧义语法包含歧义。 | 明确的语法不包含任何歧义。 |

</center>