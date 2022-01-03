# 优化完全指定机器的状态表

> 原文:[https://www . geesforgeks . org/optimization-state-of-a-complete-specific-machine/](https://www.geeksforgeeks.org/optimizing-state-table-of-a-completely-specified-machine/)

优化状态表使用基于分区的算法形成完全指定机器的给定状态表。

**示例:**

```
Input : 
6
E 0 D 1
F 0 D 0
E 0 B 1
F 0 B 0
C 0 F 1
B 0 C 0

Output :
A    E, 0    D, 1
B    F, 0    D, 0
C    E, 0    B, 1
D    F, 0    B, 0
E    C, 0    F, 1
F    B, 0    C, 0
P1=(ACE) (BDF) 
P2=(ACE) (BD) (F) 
P3=(AC) (BD) (E) (F) 
S1=(AC) S2=(BD) S3=(E) S4=(F) 
S1    S3, 0    S2, 1
S2    S4, 0    S2, 0
S3    S1, 0    S4, 1
S4    S2, 0    S1, 0 
```

**采用的方法:**

对于完全指定的状态机完全指定的状态机:

1.  如果所有输入组合的输出相同，则两个状态是等效的。接下来的状态对于所有输入组合是等效的。
2.  状态等价是将状态划分为不相交等价类的等价关系。

**机器 M1:**

<figure class="table">

| 附言（同 postscript）；警官（police sergeant） | NS，Z (x=0) | NS，Z (x=1) |
| --- | --- | --- |
| A | e，0 | d，0 |
| B | f，0 | d，0 |
| C | e，0 | b，1 |
| D | f，0 | b，0 |
| E | c，0 | f，1 |
| F | b，0 | c，0 |

*   **步骤 1(状态最小化):**识别并移除冗余状态

*   **步骤 2(状态分配):**为每个状态分配唯一的二进制代码

*   **步骤 3(组合逻辑优化):**使用未赋值的状态码，因为不在乎。
    *   **P0={(ABCDEF)}:**
        最初我们在一个分区中添加所有状态。
    *   **P1={(ACE)，(BDF)}:**
        B、D、F 比其他状态有其他投入产出响应。
    *   **P2={(ACE)、(BD)、(F)}:**
        从下一个状态的输出来看，F 比上一个分区块(BDF)的其他状态有其他的输入输出响应。
    *   **P3={(AC)、(BD)、(E)、(F)}:**
        根据下一个状态的输出，E 较上一个分区块(ACE)的其他状态有其他的输入输出响应。
    *   **P4={(AC)、(BD)、(E)、(F)} :**
        同 P3，发现等价分区。
    *   **等价划分:**
        P3，这里，P3 和 P4 是一样的，所以，我们认为 P3 是等价划分。
    *   **新州:**T2】S1 =(AC)，S2=(BD)，S3=(E)，S4=(F)

这里，状态 A、C 可以组合成一个状态，状态 B、D 可以组合成另一个状态。我们认为 S1、S2、S3、S4 是新乐观国家表中的国家。

所以，州的数量减少到了 4 个。

**以下是** **实施的办法–**

## C

```
#include <stdio.h> 
#include <stdlib.h> 
#include <string.h> 
typedef struct table { 
    int state; 
    int output; 
} table; 
int main() 
{ 
    char present_state, temp; 
    int ps, temp2; 

    // hash array 
    int hash; 

    // Input number of states 
    scanf("%d", &ps); 

    // make a table for input of next-state(NS) and output(Z) 
    table arr[2]; 
    for (int i = 0; i < ps; i++) { 
        char present_state = 'A' + i; 

        // next-state(NS) and output(Z) for x=0 
        scanf("%*c%c%d", &temp, &arr[i][0].output); 

        // generate present state(PS) 
        arr[i][0].state = (int)temp - 65; 

        // next-state(NS) and output(Z) for x=1 
        scanf("%*c%c%d", &temp, &arr[i][1].output); 

        // generate present state(PS) 
        arr[i][1].state = (int)temp - 65; 
    } 
    for (int j = 0; j < ps; j++) { 
        char present_state = 'A' + j; 
        // print the given state table 
        printf("%c %c, %d %c, %d\n", present_state, (char)(arr[j][0].state + 65), arr[j][0].output, 
                                                        (char)(arr[j][1].state + 65), arr[j][1].output); 
    } 
    int prev_result; 
    int new_result; 
    for (int i = 0; i < ps; i++) { 
        // divide P0(first partition P0=ABCDEF) according to their output in x=0, 1 
        // for x=0, x=1 whose output are same, are contained in same partition block 
        // for the example machine M1, P1 will be generated 
        // like { (ACE), (BDF) } and stored in prev_result 
        prev_result[i] = (2 * arr[i][0].output + arr[i][1].output); 
    } 
    // -------------------------------------------------------- 

    // run this function for generate n-tn Partition(Pn) 
    for (int j = 0; j < 100; j++) { 
        for (int i = 0; i < ps; i++) 

            // Load previous result in new result 
            new_result[i] = prev_result[i]; 
        for (int i = 0; i < ps; i++) 
            hash[i] = 0; 

        // ************ Update New Result **************** 

        int op = 100; 

        // print n-th partition (Pn) 
        printf("P%d=", j + 1); 
        for (int i = 0; i < ps; i++) { 

            // if i-th PS is not visited 
            if (hash[i] == 0) { 

                // make i-th PS visited 
                hash[i] = 1; 
                printf("("); 
                for (int j = i; j < ps; j++) { 
                    if (prev_result[i] == prev_result[j]) { 

                        // print n-th partition (Pn) 
                        printf("%c", j + 65); 

                        // increase i-th new-result 
                        new_result[j] = new_result[j] * op; 

                        // update new result according to next state 
                        new_result[j] += (prev_result[arr[j][0].state] * 2 + prev_result[arr[j][1].state]); 
                        hash[j] = 1; // make j-th PS visited 
                    } 
                } 
                printf(") "); 
                op += 100; 
            } 
        } 
        printf("\n"); 

        // Check New and Previous Result according to difference of e, If same 

        int flag = -1; 
        for (int x = 0; x < ps - 1; x++) { 
            for (int y = x + 1; y < ps; y++) { 
                if (prev_result[x] == prev_result[y]) { 

                    // compare difference of x-th and y-th result(new and prev) 
                    if (new_result[x] != new_result[y]) { 

                        // if difference is not same and break 
                        flag = 0; 
                        break; 
                    } 
                } 
            } 
            if (flag == 0) 
                break; 
        } 

        // ******************** Update Previous Result with new result ********************** 

        int ij = 1; 
        for (int i = 0; i < ps; i++) { 
            hash[i] = 0; 
        } 
        for (int i = 0; i < ps; i++) { 

            // if i-th PS is not visited 
            if (hash[i] == 0) { 

                // make i-th PS visited 
                hash[i] = 1; 
                for (int j = i; j < ps; j++) { 
                    if (new_result[i] == new_result[j]) { 

                        // change values of prev result with minimal value(ij) 
                        // (if Prev_result=[5, 8, 5, 5, 9], if change to [1, 2, 1, 1, 3]) 
                        prev_result[j] = ij; 
                        hash[j] = 1; // make j-th PS visited 
                    } 
                } 
                ij++; 
            } 
        } 
        // ********************************************************** 

        // Equivalent Partition Found(new result and prev result is same) 
        if (flag != 0) 
            break; 
    } 

    // ----------- generate optimistic state table ------------------ 

    int ij = 1, s; 
    for (int i = 0; i < ps; i++) { 
        hash[i] = 0; 
    } 
    for (int i = 0; i < ps; i++) { 

        // make i-th PS is not visited 
        if (hash[i] == 0) { 

            // print S-th partition block of equivalent partition 
            printf("S%d=(", ij); 

            // make i-th PS visited 
            hash[i] = 1; 
            for (int j = i; j < ps; j++) { 
                if (prev_result[i] == prev_result[j]) { 

                    // make j-th PS visited 
                    hash[j] = 1; 

                    // print S-th partition block of equivalent partition 
                    printf("%c", j + 65); 
                } 
            } 
            printf(") "); 

            // assign value of i-th PS for ij-th state 
            // of new optimistic state table 
            s[ij] = i; 
            ij++; 
        } 
    } 
    printf("\n"); 

    for (int j = 1; j < ij; j++) { 
        int present_state = j; 

        // print optimistic state table 
        printf("S%d S%d, %d S%d, %d\n", present_state, (prev_result[arr[s[j]][0].state]), 
                                                                        arr[s[j]][0].output, 
                                                            (prev_result[arr[s[j]][1].state]), 
                                                                        arr[s[j]][1].output); 
    } 

    // *********************** 
    return 0; 
} 
```

**输入:**

```
7
E 0 C 0
C 0 A 0
B 0 G 0
G 0 A 0
F 1 B 0
E 0 D 0
D 0 G 0 
```

**输出:**

```
A    E, 0    C, 0
B    C, 0    A, 0
C    B, 0    G, 0
D    G, 0    A, 0
E    F, 1    B, 0
F    E, 0    D, 0
G    D, 0    G, 0
P1=(ABCDFG) (E) 
P2=(AF) (BCDG) (E) 
P3=(AF) (BD) (CG) (E) 
P4=(A) (BD) (CG) (E) (F) 
S1=(A) S2=(BD) S3=(CG) S4=(E) S5=(F) 
S1    S4, 0    S3, 0
S2    S3, 0    S1, 0
S3    S2, 0    S3, 0
S4    S5, 1    S2, 0
S5    S4, 0    S2, 0 
```

</figure>