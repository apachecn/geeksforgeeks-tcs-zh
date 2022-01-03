# 对标准图灵机的修改

> 原文:[https://www . geesforgeks . org/对标准图灵机的修改/](https://www.geeksforgeeks.org/modifications-to-standard-turing-machine/)

标准的[图灵机](https://www.geeksforgeeks.org/turing-machine/)是一种在提供输入时向左或向右移动的机器，它可以覆盖现有的符号。

标准 TM 可以描述为 7 元组:

```
(Q, X, *, f, q0, B, F) 

where
Q is a finite set of states
X is the tape alphabet
* is the input alphabet
f is a transition function; 
   f: Q × X --> Q × X × {Left_shift, Right_shift}.

q0 is the initial state
B is the blank symbol
F is the set of final states 
```

标准的图灵机能够接受一些语言，称为递归可枚举语言。让我们看看通过做一些修改，我们是否能增加图灵机接受的语言数量。

1.  **带停留选项的图灵机:**
    如果在看到输入时不向左或向右移动，头部也可以停留在一个位置而不移动到任何地方，即

```
f: Q × X --> Q × X × {Left_shift, Right_shift, Stay}.
```

图灵机接受的语言数量仍然不变。

*   **Turing Machine with Semi-infinite tape:**
    We know that Turing machine has an infinite input tape with extends in both the directions (left and right) infinitely. So now if we restrict it to extend only in one direction and not in both the directions, i.e., we make the tape to be semi infinite, then also the number of languages accepted by the Turing machine remains same.*   **Offline Turing machine:**
    In standard Turing machine both the input and output are present on the tape, the head has the authority to move across the input and can change or modify the input, if we don’t want to modify the input we can provide the input in separate file, which is read only then the head cannot make changes to it.

    If the Turing machine wants to modify the input, the input need to be copied on the tape and the changes can be made by the head but still the input file remains unchanged as changes are made in the tape and not in the file. By doing such modification to Turing machine still the number of languages accepted by the Turing machine remains the same.*   **Jumping Turing Machine:**
    The standard Turing machine’s head can move only one step to the right or left, but in case of jumping Turing machine the head can move not only just one step to the left or right but it can move more the one, i.e., 2, 3, 4, 5, 6, … so on, or it can jump to any cell to the right or left of the input tape.

    ```
    f: Q × X --> Q × X × {Left_shift, Right_shift} x {n}
    ```

    n，是我们希望向右或向左移动的步数。但是图灵机接受的语言仍然保持不变。

    *   **Non erasing Turing Machine:**
    In standard Turing machine the input symbol can be changed to blank, but if we remove this facility of changing the input symbol to blank then such type of Turing machine is called as non erasing Turing machine . We can replace the input with any other symbol except blank. By doing this modification still the number of languages accepted by the Turing machine remains the same.*   **Always writing Turing Machine:**
    Standard Turing machine gives us the freedom that on seeing an input we can leave it as it is without doing any changes but in always writing Turing machine it is compulsory to modify the input whenever we see it we cannot leave it as it is. But this kind of modification didn’t help in increasing the number of languages accepted by the Turing machine.

    因此，我们看到，尽管对图灵机做了如此多的修改，它所接受的语言数量仍然保持不变。因此，图灵机是最强大的机器。