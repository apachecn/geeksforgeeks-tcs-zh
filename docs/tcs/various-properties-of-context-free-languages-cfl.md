# 上下文无关语言的各种属性(CFL)

> 原文:[https://www . geesforgeks . org/各种上下文无关语言属性-cfl/](https://www.geeksforgeeks.org/various-properties-of-context-free-languages-cfl/)

[上下文无关语言(CFL)](https://www.geeksforgeeks.org/check-if-the-language-is-context-free-or-not/) 是由上下文无关语法或类型 2 语法(根据乔姆斯基分类)生成并被下推自动机接受的语言。

上下文无关语言的一些非常重要的属性是:

正则性上下文无关语言是非正则 PDA 语言。

[**闭包属性**](https://www.geeksforgeeks.org/closure-properties-of-context-free-languages/) **:**
上下文无关语言在某种特定的操作下是封闭的，封闭意味着在对上下文无关语言进行该操作后，结果语言也将是上下文无关语言。一些这样操作是:

1.  联合行动
2.  串联
3.  克莱尼关闭
4.  反转操作
5.  同形
6.  逆同态
7.  代替
8.  初始化或前缀操作
9.  正则语言商
10.  循环作业
11.  与常规语言的结合
12.  与常规语言的交集
13.  与常规语言的区别

上下文无关语言在某种特定的操作下不是封闭的，非封闭意味着在对上下文无关语言执行该操作后，结果语言不再是上下文无关语言。

一些这样操作是:

1.  交集
2.  补充
3.  子集
4.  超集
5.  无限联盟
6.  差、对称差(异或、与非、或非或任何其他可简化为求交和求补的运算

[**决策属性**](https://www.geeksforgeeks.org/decidability-and-undecidability-in-toc/) **:**

1.  成员资格测试:可判定。
2.  空虚测试:可判定
3.  有限性测试:可判定的

其余决策属性在上下文无关语言中是不可判定的。

**确定性属性:**
上下文无关语言可以是:

1.  DCFL-确定性(可由确定性下推自动机识别)上下文无关语言
2.  非确定性(不能被 DPDA 识别，但 NPDA)上下文无关语言。