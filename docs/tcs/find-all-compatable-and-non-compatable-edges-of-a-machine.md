# 找出机器所有相容和不相容的边

> 原文:[https://www . geeksforgeeks . org/find-所有兼容和不兼容的机器边缘/](https://www.geeksforgeeks.org/find-all-compatable-and-non-compatable-edges-of-a-machine/)

给定机器的形式语言为 **N** 状态和 **M** 对输出组合，形式为 2D 数组 **arr[][]** 。**arr【】【】】**的每行(说 **r** )表示从**‘A’到【Z’**的节点，每对一列(说 **(a，b)** )表示节点 **r** 通过状态 **b** 到节点 **a** 的状态变化。任务是找到形式语言的相容和不相容边。
**注:** Edge(A，B)被认为是兼容的，因为在对应于每一列的 A，B 中，所有的下一个状态和输出不是相等就是未指定。
**例:**

> **输入:** N = 6，M = 4，
> arr[][]= { '-'，'-'，' C '，' 1 '，' E '，' 1 '，' B '，' 1' }，
> { 'E '，' 0 '，'-'，'-'，'-'，'-'，'-' }，
> { 'F '，' 0 '，' F '，' 1 '，'-'，'-'，'-' }，
> { '-'，'-'，' 1' } }
> **输出:**
> 不相容边
> (A，E) (A，F) (B，F) (C，E) (D，E) (D，F)
> 相容边
> (A，B)(A，C)(A，C)(B，D)(B，E)(C，D)(C，F)(E，F)
> **输入:** N = 4，M = 4，
> D '，' 1' }，
> { 'C '，' 0 '，'-'，'-'，' B '，' 0 '，' C '，' 1' } }
> **输出:**
> 不相容边
> (A，C) (A，D) (B，C) (B，D)
> 相容边
> (A，B)(C，D)

**进场:**

1.  对于所有可能的节点组合(比如 **(a，b)** )，检查在形式语言中是否存在通过任意数量状态的任何可能路径，如下所示:
    *   如果通过节点 **a** 的状态为**空**，则检查下一对节点。
    *   如果通过节点 **a** 的当前遍历状态(比如节点 **b** )不为空，并且如果通过节点 **a** 到节点 **b** 的输出状态不相同，则递归地检查从节点 **a** 到节点 **b** 的路径。
    *   如果输出状态相同，那么它在节点 **a** 和节点 **b** 之间有一条直接的边。
2.  如果路径是在任意一对节点之间找到的，那么这对节点就是兼容节点的一部分。
3.  将上述一对兼容节点存储在矩阵 **Mat[][]** 中。
4.  遍历 Mat[][]查找所有可能的对，如果该对出现在 **Mat[][]** 中，则将其打印为兼容节点，否则为不兼容节点。

下面是上述方法的实现:

## C++

```
// C++ implementation of the above approach
#include <bits/stdc++.h>
using namespace std;
const int M = 8;

// Function to find the compatible and
// non-compatible for a given formal language
void findEdges(char arr[][M], int n, int m)
{

    // To store the compatible edges
    char mat[1000][1000] = { 'x' };

    // Loop over every pair of nodes in the
    // given formal language
    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {

            // Traverse through the output
            // column and compare it between
            // each set of pairs of nodes
            for (int k = 0; k < 2 * m; k += 2) {

                // If the the output is not
                // specified then leave the
                // edge unprocessed
                if (arr[i][k + 1] == '-'
                    || arr[j][k + 1] == '-') {
                    continue;
                }

                // If the output of states
                // doesn't match then not
                // compatable.
                if (arr[i][k + 1] != arr[j][k + 1]) {

                    // Mark the not compatable
                    // edges in the maxtrix with
                    // character 'v'
                    mat[i][j] = 'v';
                    mat[j][i] = 'v';
                    break;
                }
            }
        }
    }

    int nn = n;

    // Loop over all node to find other non
    // compatable edges
    while (nn--) {

        // Loop over every pair of nodes in
        // the given formal language
        for (int i = 0; i < n; i++) {
            for (int j = i + 1; j < n; j++) {

                int k;
                for (k = 0; k < m; k += 2) {

                    // If the the output is
                    // not specified then
                    // leave edge unprocessed
                    if (arr[i][k + 1] == '-'
                        || arr[j][k + 1] == '-') {
                        continue;
                    }

                    // If output is not equal
                    // then break as non-compatable
                    if (arr[i][k + 1] != arr[j][k + 1]) {
                        break;
                    }
                }

                if (k < m) {
                    continue;
                }

                for (k = 0; k < m; k += 2) {

                    // If next states are unspecified
                    // then continue
                    if (arr[i][k] == '-'
                        || arr[j][k] == '-') {
                        continue;
                    }

                    // If the states are not equal
                    if (arr[i][k] != arr[j][k]) {
                        int x = arr[i][k] - 'A';
                        int y = arr[j][k] - 'A';

                        // If the dependent edge
                        // is not compatable then
                        // this edge is also not
                        // compatable
                        if (mat[x][y] == 'v') {
                            mat[i][j] = 'v';
                            mat[j][i] = 'v';
                            break;
                        }
                    }
                }
            }
        }
    }

    // Output all Non-compatable Edges
    printf("Not Compatable Edges \n");
    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {
            if (mat[i][j] == 'v') {
                printf("(%c, %c) ", i + 65, j + 65);
            }
        }
    }
    printf("\n");

    // Output all Compatable Edges
    printf("Compatable Edges \n");
    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {
            if (mat[i][j] != 'v') {
                printf("(%c, %c)", i + 65, j + 65);
            }
        }
    }
}

// Driver Code
int main()
{
    int n = 6, m = 4;

    char arr[][8] = { { '-', '-', 'C', '1', 'E', '1', 'B', '1' },
                      { 'E', '0', '-', '-', '-', '-', '-', '-' },
                      { 'F', '0', 'F', '1', '-', '-', '-', '-' },
                      { '-', '-', '-', '-', 'B', '1', '-', '-' },
                      { '-', '-', 'F', '0', 'A', '0', 'D', '1' },
                      { 'C', '0', '-', '-', 'B', '0', 'C', '1' } };

    findEdges(arr, n, m);
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java implementation of the above approach
import java.util.*;

class GFG{

static int M = 8;

// Function to find the compatible and
// non-compatible for a given formal language
static void findEdges(char arr[][], int n, int m)
{

    // To store the compatible edges
    char [][]mat = new char[1000][1000];

    // Loop over every pair of nodes in the
    // given formal language
    for(int i = 0; i < n; i++)
    {
        for(int j = i + 1; j < n; j++)
        {

            // Traverse through the output
            // column and compare it between
            // each set of pairs of nodes
            for(int k = 0; k < 2 * m; k += 2)
            {

                // If the the output is not
                // specified then leave the
                // edge unprocessed
                if (arr[i][k + 1] == '-' ||
                    arr[j][k + 1] == '-')
                {
                    continue;
                }

                // If the output of states
                // doesn't match then not
                // compatable.
                if (arr[i][k + 1] != arr[j][k + 1])
                {

                    // Mark the not compatable
                    // edges in the maxtrix with
                    // character 'v'
                    mat[i][j] = 'v';
                    mat[j][i] = 'v';
                    break;
                }
            }
        }
    }

    int nn = n;

    // Loop over all node to find other non
    // compatable edges
    while (nn-- > 0)
    {

        // Loop over every pair of nodes in
        // the given formal language
        for(int i = 0; i < n; i++)
        {
            for(int j = i + 1; j < n; j++)
            {
                int k;
                for(k = 0; k < m; k += 2)
                {

                    // If the the output is
                    // not specified then
                    // leave edge unprocessed
                    if (arr[i][k + 1] == '-' ||
                        arr[j][k + 1] == '-')
                    {
                        continue;
                    }

                    // If output is not equal
                    // then break as non-compatable
                    if (arr[i][k + 1] !=
                        arr[j][k + 1])
                    {
                        break;
                    }
                }

                if (k < m)
                {
                    continue;
                }

                for(k = 0; k < m; k += 2)
                {

                    // If next states are unspecified
                    // then continue
                    if (arr[i][k] == '-' ||
                        arr[j][k] == '-')
                    {
                        continue;
                    }

                    // If the states are not equal
                    if (arr[i][k] != arr[j][k])
                    {
                        int x = arr[i][k] - 'A';
                        int y = arr[j][k] - 'A';

                        // If the dependent edge
                        // is not compatable then
                        // this edge is also not
                        // compatable
                        if (mat[x][y] == 'v')
                        {
                            mat[i][j] = 'v';
                            mat[j][i] = 'v';
                            break;
                        }
                    }
                }
            }
        }
    }

    // Output all Non-compatable Edges
    System.out.printf("Not Compatable Edges \n");
    for(int i = 0; i < n; i++)
    {
        for(int j = i + 1; j < n; j++)
        {
            if (mat[i][j] == 'v')
            {
                System.out.printf("(%c, %c) ",
                                  i + 65, j + 65);
            }
        }
    }
    System.out.printf("\n");

    // Output all Compatable Edges
    System.out.printf("Compatable Edges \n");
    for(int i = 0; i < n; i++)
    {
        for(int j = i + 1; j < n; j++)
        {
            if (mat[i][j] != 'v')
            {
                System.out.printf("(%c, %c)",
                                  i + 65, j + 65);
            }
        }
    }
}

// Driver Code
public static void main(String[] args)
{
    int n = 6, m = 4;

    char arr[][] = { { '-', '-', 'C', '1',
                       'E', '1', 'B', '1' },
                     { 'E', '0', '-', '-',
                       '-', '-', '-', '-' },
                     { 'F', '0', 'F', '1',
                       '-', '-', '-', '-' },
                     { '-', '-', '-', '-',
                       'B', '1', '-', '-' },
                     { '-', '-', 'F', '0',
                       'A', '0', 'D', '1' },
                     { 'C', '0', '-', '-',
                       'B', '0', 'C', '1' } };

    findEdges(arr, n, m);
}
}

// This code is contributed by Amit Katiyar
```

## C#

```
// C# implementation of
// the above approach
using System;
class GFG{

static int M = 8;

// Function to find the
//compatible and non-compatible
// for a given formal language 
static void findEdges(char [,]arr,
                      int n, int m)
{
  // To store the compatible edges
  char [,]mat = new char[1000, 1000];

  // Loop over every pair of
  // nodes in the given
  // formal language
  for(int i = 0; i < n; i++)
  {
    for(int j = i + 1; j < n; j++)
    {
      // Traverse through the output
      // column and compare it between
      // each set of pairs of nodes
      for(int k = 0; k < 2 * m; k += 2)
      {
        // If the the output is not
        // specified then leave the
        // edge unprocessed
        if (arr[i, k + 1] == '-' ||
            arr[j, k + 1] == '-')
        {
          continue;
        }

        // If the output of states
        // doesn't match then not
        // compatable.
        if (arr[i, k + 1] != arr[j, k + 1])
        {
          // Mark the not compatable
          // edges in the maxtrix with
          // character 'v'
          mat[i, j] = 'v';
          mat[j, i] = 'v';
          break;
        }
      }
    }
  }

  int nn = n;

  // Loop over all node to find other non
  // compatable edges
  while (nn-- > 0)
  {

    // Loop over every pair of nodes in
    // the given formal language
    for(int i = 0; i < n; i++)
    {
      for(int j = i + 1; j < n; j++)
      {
        int k;
        for(k = 0; k < m; k += 2)
        {
          // If the the output is
          // not specified then
          // leave edge unprocessed
          if (arr[i, k + 1] == '-' ||
              arr[j, k + 1] == '-')
          {
            continue;
          }

          // If output is not equal
          // then break as non-compatable
          if (arr[i, k + 1] !=
              arr[j, k + 1])
          {
            break;
          }
        }

        if (k < m)
        {
          continue;
        }

        for(k = 0; k < m; k += 2)
        {
          // If next states are unspecified
          // then continue
          if (arr[i, k] == '-' ||
              arr[j, k] == '-')
          {
            continue;
          }

          // If the states are not equal
          if (arr[i, k] != arr[j, k])
          {
            int x = arr[i, k] - 'A';
            int y = arr[j, k] - 'A';

            // If the dependent edge
            // is not compatable then
            // this edge is also not
            // compatable
            if (mat[x, y] == 'v')
            {
              mat[i, j] = 'v';
              mat[j, i] = 'v';
              break;
            }
          }
        }
      }
    }
  }

  // Output all Non-compatable Edges
  Console.Write("Not Compatable Edges \n");
  for(int i = 0; i < n; i++)
  {
    for(int j = i + 1; j < n; j++)
    {
      if (mat[i, j] == 'v')
      {
        Console.Write("({0}, {1}) ",
                      (char)(i + 65),
                      (char)(j + 65));
      }
    }
  }
  Console.Write("\n");

  // Output all Compatable Edges
  Console.Write("Compatable Edges \n");
  for(int i = 0; i < n; i++)
  {
    for(int j = i + 1; j < n; j++)
    {
      if (mat[i, j] != 'v')
      {
        Console.Write("({0}, {1})",
                      (char)(i + 65),
                      (char)(j + 65));
      }
    }
  }
}

// Driver Code
public static void Main(String[] args)
{
  int n = 6, m = 4;
  char [,]arr = {{'-', '-', 'C', '1',
                  'E', '1', 'B', '1'},
                 {'E', '0', '-', '-',
                  '-', '-', '-', '-'},
                 {'F', '0', 'F', '1',
                  '-', '-', '-', '-'},
                 {'-', '-', '-', '-',
                  'B', '1', '-', '-'},
                 {'-', '-', 'F', '0',
                  'A', '0', 'D', '1'},
                 {'C', '0', '-', '-',
                  'B', '0', 'C', '1'}};
  findEdges(arr, n, m);
}
}

// This code is contributed by 29AjayKumar
```

**Output:** 

```
Not Compatable Edges
(A, E) (A, F) (B, F) (C, E) (D, E) (D, F) 
Compatable Edges
(A, B)(A, C)(A, D)(B, C)(B, D)(B, E)(C, D)(C, F)(E, F)

```

**时间复杂度:** O(M*N <sup>3</sup> ，其中 N 为状态数，M 为每个状态的输出。