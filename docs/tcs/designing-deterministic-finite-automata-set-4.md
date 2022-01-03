# 设计确定性有限自动机(集合 4)

> 原文:[https://www . geeksforgeeks . org/design-design-determinative-有限自动机-set-4/](https://www.geeksforgeeks.org/designing-deterministic-finite-automata-set-4/)

**先决条件:** [设计有限自动机](https://www.geeksforgeeks.org/designing-finite-automata-from-regular-expression/)[设计确定性有限自动机(集合 3)](https://www.geeksforgeeks.org/toc-designing-deterministic-finite-automata-set-3/)
在本文中，我们将看到确定性有限自动机(DFA)的一些设计。

**问题-1:** 在{a，b}上构造一个接受字符串集的最小 DFA，其中每个“a”后面跟一个“b”。
**解释:**想要的语言会是这样的:

```
L1 = {ε, ab, abab, abbbb, ababababab, ..............}
```

在这里我们可以看到，包含“a”的语言的每个字符串后面都跟着“b”，但是下面的语言不被这个 DFA 接受，因为下面语言的一些字符串不包含“a”后面跟着“b”。

```
L2 = {ba, baab, bbaba, ..............}
```

在上面的 DFA 中，状态“W”也是初始和最终状态，当得到“b”作为输入时，它保持在自身状态，当得到“a”作为输入时，它过渡到正常状态“X”，当得到“b”作为输入时，它过渡到最终状态“W”。获得“a”作为输入时的状态“X”转变为死状态“Z”。状态“Z”被称为死状态，因为一旦获得任何输入，它就永远无法过渡到最终状态。

```
def stateW(n):
    if(len(n)==0):
        print("Accepted")
    else:  

        #if 'a' found 
        #call function stateX
        if (n[0]=='a' ):
            stateX(n[1:])
        #if 'b' found 
        #call function stateW    
        elif (n[0]=='b' ):
            stateW(n[1:])    

def stateX(n):
    if(len(n)==0):
        print("Not Accepted")
    else:  

        #if 'a' found 
        #call function stateZ
        if (n[0]=='a' ):
            stateZ(n[1:])

        #if 'b' found 
        #call function stateW     
        elif (n[0]=='b' ):
            stateW(n[1:]) 

def stateZ(n):
    if(len(n)==0):
        print("Not Accepted")
    else:

         #if a or b found 
         #call stateZ
        if (n[0]=='a' or n[0]=='b'):
            stateZ(n[1:])              

#take input
n=input()

#call stateA
#to check the input
stateA(n)
```

**问题-2:** 在{a，b}上构造一个接受字符串的最小 DFA 集合，其中每个“a”后面都不跟“b”
**解释:**所需的语言如下:

```
L1 = {ε, a, aa, aaaa, b, bba, bbbbba..............}
```

在这里，我们可以看到，包含“a”的语言的每个字符串后面都不会跟“b”，但是下面的语言不被这个 DFA 接受，因为下面包含“a”的语言的一些字符串后面会跟“b”。

```
L2 = {ba, baab, bbaba, ..............}
```

在上面的 DFA 中，状态“X”是初始和最终状态，当得到“b”作为输入时，它保持自身的状态，当得到“a”作为输入时，它过渡到最终状态“Y”，当得到“a”作为输入时，它保持自身的状态，当得到“b”作为输入时，它过渡到死状态“Z”。状态“Z”被称为死状态，这是因为它永远不能进入任何最终状态。

```
def stateX(n):
    if(len(n)==0):
        print("Accepted")
    else:  

        #if 'a' found 
        #call function stateY
        if (n[0]=='a' ):
            stateY(n[1:])
        #if 'b' found 
        #call function stateX   
        elif (n[0]=='b' ):
            stateX(n[1:])    

def stateY(n):
    if(len(n)==0):
        print("Accepted")
    else:  

        #if 'a' found 
        #call function stateZ
        if (n[0]=='a' ):
            stateZ(n[1:])

        #if 'b' found 
        #call function stateY   
        elif (n[0]=='b' ):
            stateY(n[1:]) 

def stateZ(n):
    if(len(n)==0):
        print("Not Accepted")
    else:

         #if a or b found 
         #call stateZ
        if (n[0]=='a' or n[0]=='b'):
            stateZ(n[1:])              

#take input
n=input()

#call stateA
#to check the input
stateA(n)
```