# 不以“THE”结尾的字符串的 DFA

> 原文:[https://www . geesforgeks . org/DFA-for-string-not-end-the/](https://www.geeksforgeeks.org/dfa-for-strings-not-ending-with-the/)

**问题–**接受不以子字符串“THE”结尾的字符串。检查给定的字符串是否以“the”结尾。字符串末尾避免的“The”的不同形式有:

```
"THE", "ThE", "THe", "tHE", "thE", "The", "tHe" and "the"
```

所有以任何上述形式的“the”结尾的字符串都不被接受。

**确定不以“THE”–**
结尾的字符串的有限自动机(dfa)这个 DFA 中的初始和开始状态是 Qo

![](img/91379cd8fc7a4f69f6d273c315d85348.png)

**程序中使用的方法–**
在本程序中，考虑 4 个状态为 0、1、2 和 3。现在让我们取一个名为 DFA 的变量，它最初将是 0。每当任何转换发生时，它都会用与新状态相关联的数字来更新 DFA 的值。

**示例:**如果发生从状态 0 到状态 1 的转换，则 DFA 的值将更新为 1。如果从状态 2 转换到状态 3，则 dfa 的值将更新为 3。这样，在整个字符串上应用这个算法，如果最终达到状态 0、1 或 2，那么我们的字符串将被接受，否则不会。

```
Input : XYzabCthe
Output : NOT ACCEPTED

Input :  Themaliktth
Output :  ACCEPTED
```

## C++

```
// C++ program to implement DFS that accepts
// all string that do not end with "THE"
#include <iostream>
using namespace std;

// dfa tells the number associated
// with the present state
int dfa = 0;

// This function is for
// the starting state (zeroth) of DFA
void start(char c)
{

    // On receiving 'T' or 't' goto
    // first state (1)
    if (c == 't' || c == 'T')
        dfa = 1;
}

// This function is for the first state of DFA
void state1(char c)
{

    // On receiving 'T' or 't' goto
    // first state (1)
    if (c == 't' || c == 'T')
        dfa = 1;

    // On receiving 'H' or 'h'
    // goto second state (2)
    else if (c == 'h' || c == 'H')
        dfa = 2;

    // Else goto starting state (0)
    else
        dfa = 0;
}

// This function is for the second state of DFA
void state2(char c)
{

    // On receiving 'E' or 'e' goto third state (3)
    // else goto starting state (0)
    if (c == 'e' || c == 'E')
        dfa = 3;
    else if (c == 't' || c == 'T')
        dfa = 1;
      else
        dfa = 0;
}

// This function is for the third state of DFA
void state3(char c)
{

    // On receiving 'T' or 't' goto first state (1)
    // else goto starting state (0)
    if (c == 't' || c == 'T')
        dfa = 1;
    else
        dfa = 0;
}

bool isAccepted(string str)
{

    // Store length of string
    int len = str.length();

    for(int i = 0; i < len; i++)
    {
        if (dfa == 0)
            start(str[i]);

        else if (dfa == 1)
            state1(str[i]);

        else if (dfa == 2)
            state2(str[i]);

        else
            state3(str[i]);       
    }
    return (dfa != 3);
}

// Driver code
int main()
{
    string str = "forTHEgeeks";
    if (isAccepted(str) == true)
        cout << "ACCEPTED\n";
    else
        cout << "NOT ACCEPTED\n";

    return 0;
}

// This code is contributed by ShubhamSingh10
```

## C

```
// C program to implement DFS that accepts
// all string that do not end with "THE"
#include <stdio.h>
#include <string.h>

// dfa tells the number associated
// with the present state
int dfa = 0;

// This function is for
// the starting state (zeroth) of DFA
void start(char c)
{
    // On receiving 'T' or 't' goto first state (1)
    if (c == 't' || c == 'T')
        dfa = 1;
}

// This function is for the first state of DFA
void state1(char c)
{
    // On receiving 'T' or 't' goto first state (1)
    if (c == 't' || c == 'T')
        dfa = 1;

    // On receiving 'H' or 'h' goto second state (2)
    else if (c == 'h' || c == 'H')
        dfa = 2;

    // else goto starting state (0)
    else
        dfa = 0;
}

// This function is for the second state of DFA
void state2(char c)
{
    // On receiving 'E' or 'e' goto third state (3)
    // else goto starting state (0)
    if (c == 'e' || c == 'E')
        dfa = 3;
    else if (c == 't' || c == 'T')
        dfa = 1;
      else
        dfa = 0;
}

// This function is for the third state of DFA
void state3(char c)
{
    // On receiving 'T' or 't' goto first state (1)
    // else goto starting state (0)
    if (c == 't' || c == 'T')
        dfa = 1;
    else
        dfa = 0;
}

bool isAccepted(char str[])
{
    // store length of string
    int len = strlen(str);

    for (int i=0; i < len; i++) {
            if (dfa == 0)
                start(str[i]);

            else if (dfa == 1)
                state1(str[i]);

            else if (dfa == 2)
                state2(str[i]);

            else
                state3(str[i]);       
    }

    return (dfa != 3);
}

// driver code
int main()
{
    char str[] = "forTHEgeeks";
    if (isAccepted(str) == true)
        printf("ACCEPTED\n");
    else
        printf("NOT ACCEPTED\n");
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to implement DFS that accepts
// all string that do not end with "THE"
import java.util.*;

class GFG
{

// dfa tells the number associated
// with the present state
static int dfa = 0;

// This function is for
// the starting state (zeroth) of DFA
static void start(char c)
{
    // On receiving 'T' or 't' goto first state (1)
    if (c == 't' || c == 'T')
        dfa = 1;
}

// This function is for the first state of DFA
static void state1(char c)
{
    // On receiving 'T' or 't' goto first state (1)
    if (c == 't' || c == 'T')
        dfa = 1;

    // On receiving 'H' or 'h' goto second state (2)
    else if (c == 'h' || c == 'H')
        dfa = 2;

    // else goto starting state (0)
    else
        dfa = 0;
}

// This function is for the second state of DFA
static void state2(char c)
{
    // On receiving 'E' or 'e' goto third state (3)
    // else goto starting state (0)
    if (c == 'e' || c == 'E')
        dfa = 3;
    else
        dfa = 0;
}

// This function is for the third state of DFA
static void state3(char c)
{
    // On receiving 'T' or 't' goto first state (1)
    // else goto starting state (0)
    if (c == 't' || c == 'T')
        dfa = 1;
    else
        dfa = 0;
}

static boolean isAccepted(char str[])
{
    // store length of string
    int len = str.length;

    for (int i=0; i < len; i++)
    {
            if (dfa == 0)
                start(str[i]);

            else if (dfa == 1)
                state1(str[i]);

            else if (dfa == 2)
                state2(str[i]);

            else
                state3(str[i]);    
    }

    return (dfa != 3);
}

// Driver code
public static void main(String[] args)
{
    char str[] = "forTHEgeeks".toCharArray();
    if (isAccepted(str) == true)
        System.out.println("ACCEPTED\n");
    else
        System.out.println("NOT ACCEPTED\n");
}
}

/* This code is contributed by PrinciRaj1992 */
```

## 蟒蛇 3

```
# Python3 program to implement DFS that accepts
# all stringing that do not end with "THE"

# This function is for the starting
# state (zeroth) of DFA
def start(c):

    # On receiving 'T' or 't' goto
    # first state (1)
    if (c == 't' or c == 'T'):
        dfa=1

# This function is for the first state of DFA
def state1(c):

    # On receiving 'T' or 't' goto first state (1)
    if (c == 't' or c == 'T'):
        dfa = 1

    # On receiving 'H' or 'h' goto second state (2)
    elif (c == 'h' or c == 'H'):
        dfa = 2

    # else goto starting state (0)
    else:
        dfa = 0

# This function is for the second state of DFA
def state2(c):

    # On receiving 'E' or 'e' goto third
    # state (3) else goto starting state (0)
    if (c == 'e' or c == 'E'):
        dfa = 3
    else:
        dfa = 0

# This function is for the third state of DFA
def state3(c):

    # On receiving 'T' or 't' goto first
    # state (1) else goto starting state (0)
    if (c == 't' or c == 'T'):
        dfa = 1
    else:
        dfa = 0

def isAccepted(string):

    # store length of stringing
    length = len(string)

    for i in range(length):
        if (dfa == 0):
            start(string[i])
        elif (dfa == 1):
            state1(string[i])
        elif (dfa == 2):
            state2(string[i])
        else:
            state3(string[i])        
    return (dfa != 3)

# Driver Code
if __name__ == "__main__" :
    string="forTHEgeeks"

    # dfa tells the number associated
    # with the present state
    dfa = 0
    if isAccepted(string):
        print("ACCEPTED")
    else:
        print("NOT ACCEPTED")

# This code is contributed by SHUBHAMSINGH10
```

## C#

```
// C# program to implement DFS that accepts
// all string that do not end with "THE"
using System;

class GFG
{

// dfa tells the number associated
// with the present state
static int dfa = 0;

// This function is for
// the starting state (zeroth) of DFA
static void start(char c)
{
    // On receiving 'T' or 't' goto first state (1)
    if (c == 't' || c == 'T')
        dfa = 1;
}

// This function is for the first state of DFA
static void state1(char c)
{
    // On receiving 'T' or 't' goto first state (1)
    if (c == 't' || c == 'T')
        dfa = 1;

    // On receiving 'H' or 'h' goto second state (2)
    else if (c == 'h' || c == 'H')
        dfa = 2;

    // else goto starting state (0)
    else
        dfa = 0;
}

// This function is for the second state of DFA
static void state2(char c)
{
    // On receiving 'E' or 'e' goto third state (3)
    // else goto starting state (0)
    if (c == 'e' || c == 'E')
        dfa = 3;
    else
        dfa = 0;
}

// This function is for the third state of DFA
static void state3(char c)
{
    // On receiving 'T' or 't' goto first state (1)
    // else goto starting state (0)
    if (c == 't' || c == 'T')
        dfa = 1;
    else
        dfa = 0;
}

static bool isAccepted(char []str)
{
    // store length of string
    int len = str.Length;

    for (int i=0; i < len; i++)
    {
            if (dfa == 0)
                start(str[i]);

            else if (dfa == 1)
                state1(str[i]);

            else if (dfa == 2)
                state2(str[i]);

            else
                state3(str[i]);
    }

    return (dfa != 3);
}

// Driver code
static public void Main ()
{
    char []str = "forTHEgeeks".ToCharArray();
    if (isAccepted(str) == true)
        Console.WriteLine("ACCEPTED\n");
    else
        Console.WriteLine("NOT ACCEPTED\n");
}
}

/* This code is contributed by ajit. */
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```
<?php
// PHP program to implement DFS
// that accepts all string that
// do not end with "THE"

// dfa tells the number associated
// with the present state
$dfa = 0;

// This function is for the
// starting state (zeroth) of DFA
function start($c)
{
    global $dfa;
    // On receiving 'T' or 't'
    // goto first state (1)
    if ($c == 't' || $c == 'T')
        $dfa = 1;
}

// This function is for
// the first state of DFA
function state1($c)
{
    global $dfa;
    // On receiving 'T' or 't'
    // goto first state (1)
    if ($c == 't' || $c == 'T')
        $dfa = 1;

    // On receiving 'H' or 'h'
    // goto second state (2)
    else if ($c == 'h' || $c == 'H')
        $dfa = 2;

    // else goto starting state (0)
    else
        $dfa = 0;
}

// This function is for
// the second state of DFA
function state2($c)
{
    global $dfa;
    // On receiving 'E' or 'e'
    // goto third state (3) else
    // goto starting state (0)
    if ($c == 'e' || $c == 'E')
        $dfa = 3;
    else
        $dfa = 0;
}

// This function is for
// the third state of DFA
function state3($c)
{
    global $dfa;
    // On receiving 'T' or 't'
    // goto first state (1) else
    // goto starting state (0)
    if ($c == 't' || $c == 'T')
        $dfa = 1;
    else
        $dfa = 0;
}

function isAccepted($str)
{
    global $dfa;
    // store length of string
    $len = strlen($str);

    for ($i=0; $i < $len; $i++)
    {
            if ($dfa == 0)
                start($str[$i]);

            else if ($dfa == 1)
                state1($str[$i]);

            else if ($dfa == 2)
                state2($str[$i]);

            else
                state3($str[$i]);
    }

    return ($dfa != 3);
}

// Driver Code
$str = "forTHEgeeks";
if (isAccepted($str) == true)
    echo "ACCEPTED\n";
else
    echo "NOT ACCEPTED\n";

// This code is contributed by m_kit
?>
```

## java 描述语言

```
<script>

    // Javascript program to
    // implement DFS that accepts
    // all string that do not end
    // with "THE"

    // dfa tells the number associated
    // with the present state
    let dfa = 0;

    // This function is for
    // the starting state (zeroth) of DFA
    function start(c)
    {
        // On receiving 'T' or 't' goto
        // first state (1)
        if (c == 't' || c == 'T')
            dfa = 1;
    }

    // This function is for the first state of DFA
    function state1(c)
    {
        // On receiving 'T' or 't' goto first state (1)
        if (c == 't' || c == 'T')
            dfa = 1;

        // On receiving 'H' or 'h' goto second state (2)
        else if (c == 'h' || c == 'H')
            dfa = 2;

        // else goto starting state (0)
        else
            dfa = 0;
    }

    // This function is for the second state of DFA
    function state2(c)
    {
        // On receiving 'E' or 'e' goto third state (3)
        // else goto starting state (0)
        if (c == 'e' || c == 'E')
            dfa = 3;
        else
            dfa = 0;
    }

    // This function is for the third state of DFA
    function state3(c)
    {
        // On receiving 'T' or 't' goto first state (1)
        // else goto starting state (0)
        if (c == 't' || c == 'T')
            dfa = 1;
        else
            dfa = 0;
    }

    function isAccepted(str)
    {
        // store length of string
        let len = str.length;

        for (let i=0; i < len; i++)
        {
                if (dfa == 0)
                    start(str[i]);

                else if (dfa == 1)
                    state1(str[i]);

                else if (dfa == 2)
                    state2(str[i]);

                else
                    state3(str[i]);
        }

        return (dfa != 3);
    }

    let str = "forTHEgeeks".split('');
    if (isAccepted(str) == true)
        document.write("ACCEPTED");
    else
        document.write("NOT ACCEPTED");

</script>
```

**Output :** 

```
ACCEPTED
```

这个程序的时间复杂度是 O(n)