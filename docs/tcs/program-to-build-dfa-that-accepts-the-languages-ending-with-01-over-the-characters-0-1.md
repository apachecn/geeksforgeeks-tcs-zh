# 构建 DFA 的程序，该程序接受字符{0，1}

上以“01”结尾的语言

> 原文:[https://www . geeksforgeeks . org/program-to-build-DFA-接受语言-以-01 结束-字符-0-1/](https://www.geeksforgeeks.org/program-to-build-dfa-that-accepts-the-languages-ending-with-01-over-the-characters-0-1/)

给定一个二进制字符串 **str** ，任务是构建一个接受以**“01”**结尾的语言而不是字符 **{0，1}** 的 DFA。

**示例:**

> **输入:** str = "00011101"
> **输出:**字符串接受
> **解释:**
> 由于给定字符串以“01”结尾，因此被接受。
> 
> **输入:** str = "00001111"
> **输出:**字符串被拒绝
> **解释:**
> 由于给定字符串以“11”结尾，因此被拒绝。

**方法:**解决上述问题，下面是需要的类状态和成员函数:

*   **配对 1:** 它处理第一种类型的输入，即 0，并将其与指向下一个状态的对象指针相链接。
*   **配对 2:** 它处理第二种类型的输入，即 1，并将其与指向下一个状态的对象指针相链接。
*   **m_x:** 它定义一个特定的状态是初始的还是最终的。

类成员函数定义如下:

*   **initialize():** 该函数将两对(用于两种输入)作为参数，并带有状态定义字符(I 或 f)。
*   **transition():** 它充当自动机的转换表，通过特定的输入，它从一个状态进入下一个状态。
*   **traverse():** 这个函数接受输入字符串，并将其传递给自动机。
*   **检查():**该功能检查输入结束后，结束状态是否为最终状态。如果它是最终的，则该字符串被接受，否则被拒绝。

这个问题需要三种状态。因此，创建三类对象并用所需的值初始化它们，如下所示:

*   **状态 1:** 输入 0 时进入状态 2，输入 1 时进入自身。
*   **状态 2:** 在输入 0 时，它转到自身，在输入 1 时，它转到状态 3。
*   **状态 3:** 输入 0 时进入状态 2，输入 1 时进入状态 1。还有，这是我们最后的状态。

以下是上述方法的实现:

## C++14

```
// C++ program of a DFA that accepts
// all string ending with "01"

#include <iostream>
#include <string>
using namespace std;

// Class for automata
class State {
private:
    // Data members to store the input
    pair<int, State*> Pair1;
    pair<int, State*> Pair2;
    char m_x;

public:
    // Pointer to the state of automata
    static State* m_ptr;

    // Constructor to initialize state
    State()
    {
        Pair1.first = 0;
        Pair1.second = nullptr;
        Pair2.first = 0;
        Pair2.second = nullptr;
        m_x = ' ';
    }

    // Initialise pair1 and pair2
    // with state x
    void initialize(
        pair<int, State*> pair1,
        pair<int, State*> pair2, char x)
    {
        Pair1 = pair1;
        Pair2 = pair2;
        m_x = x;
    }

    // Passes a string through automata
    static void transition(int input);
    static void traverse(string& str, int n);

    // Checks if the last state
    // is final or not
    static void check();
};

// Pointer to the current
// state of automata
State* State::m_ptr{ nullptr };

// Function to provide state
// transition of automata
void State::transition(int input)
{
    if ((*m_ptr).Pair1.first == input)
        m_ptr = (*m_ptr).Pair1.second;
    else
        m_ptr = (*m_ptr).Pair2.second;
}

// Checks if the last state
// is final or not
void State::check()
{
    if ((*m_ptr).m_x == 'f')
        cout << "String Accepted\n"
             << endl;
    else
        cout << "String Rejected\n"
             << endl;
}

// Passes a string through automata
void State::traverse(string& str, int n)
{
    for (int i = 0; i < n; i++) {
        int x{ (int)str[i] - (int)'0' };
        transition(x);
    }
}

// Function to check if the given
// is accepted in DFA or not
void isAccepted(string str)
{
    // States of the automata
    State one, two, three;

    // Transition table for required
    // automata
    one.initialize({ 0, &two },
                   { 1, &one }, 'i');
    two.initialize({ 0, &two },
                   { 1, &three }, 'i');
    three.initialize({ 0, &two },
                     { 1, &one }, 'f');

    int length{ static_cast<int>(str.length()) };
    State::m_ptr = &one;

    // Function call
    State::traverse(str, length);
    State::check();
}

// Driver Code
int main()
{
    string str{ "00111101" };

    isAccepted(str);

    return 0;
}
```

**Output:**

```
String Accepted

```

***时间复杂度:** O(N)
**辅助空间:** O(1)*