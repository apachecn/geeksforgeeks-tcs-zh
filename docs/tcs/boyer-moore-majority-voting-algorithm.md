# 博耶-摩尔多数投票算法

> 原文:[https://www . geesforgeks . org/boyer-Moore-多数投票-算法/](https://www.geeksforgeeks.org/boyer-moore-majority-voting-algorithm/)

**博耶-摩尔投票**算法是一种流行的优化算法，用于在出现次数超过 N/ 2 次的给定元素中寻找多数元素。这对于找到在给定元素上进行 2 次遍历的多数元素非常有效，这在 O(N)时间复杂度和 O(1)空间复杂度下有效。

举个例子，让我们看看其工作背后的算法和直觉

```
Input :{1,1,1,1,2,3,5}
Output : 1
Explanation : 1 occurs more than 3 times.
Input : {1,2,3}
Output : -1
```

该算法的原理是，如果一个元素出现的次数超过 N/2 次，这意味着除此之外的其余元素肯定会少于 N/2 次。所以让我们检查算法的进程。

*   首先，从给定的一组元素中选择一个候选元素，如果它与候选元素相同，则增加投票。否则，如果票数变为 0，则减少票数，选择另一个新元素作为新候选人。

**工作背后的直觉:**
当元素与候选元素相同时，当发现某个其他元素与候选元素不相等时，投票会增加。我们减少了计数。这实际上意味着我们正在降低所选候选人获胜能力的优先级，因为我们知道，如果候选人是多数，它出现的次数会超过 N/2 次，而剩余的元素会少于 N/2 次。我们不断减少选票，因为我们发现了一些与候选元素不同的元素。当票数变为 0 时，这实际上意味着存在相同数量的不同元素，这不应该是元素为多数元素的情况。所以候选元素不能是大多数，所以我们选择现在的元素作为候选，并继续相同的操作，直到所有元素都完成。最终候选人将是我们的多数派。我们使用第二次遍历来检查它的计数是否大于 N/2。如果这是真的，我们认为它是多数要素。

**实现该算法的步骤:**
**步骤 1–**找到占多数的候选人–

*   初始化一个变量说 **i，票数= 0，候选人=-1**
*   使用 for 循环遍历数组
*   如果**票数= 0，**选择**候选人= arr【I】**，使**票数=1** 。
*   否则，如果当前元素与候选增量票相同
*   否则会减少票数。

**第 2 步–**检查候选人的票数是否超过 N/2–

*   初始化一个变量计数=0，如果它与候选值相同，则递增计数。
*   如果计数大于 N/2，则返回候选人。
*   否则返回-1。

```
Dry run for the above example: 
Given :
  arr[]=        1    1    1    1    2    3    5
 votes =0       1    2    3    4    3    2    1
 candidate = -1 1    1    1    1    1    1    1
 candidate = 1  after first traversal
                1    1    1    1    2    3    5
 count =0       1    2    3    4    4    4    4 
 candidate = 1  
 Hence count > 7/2 =3
 So 1 is the majority element.
```

## C++

```
// C++ implementation for the above approach
#include <iostream>
using namespace std;
// Function to find majority element
int findMajority(int arr[], int n)
{
    int i, candidate = -1, votes = 0;
    // Finding majority candidate
    for (i = 0; i < n; i++) {
        if (votes == 0) {
            candidate = arr[i];
            votes = 1;
        }
        else {
            if (arr[i] == candidate)
                votes++;
            else
                votes--;
        }
    }
    int count = 0;
    // Checking if majority candidate occurs more than n/2
    // times
    for (i = 0; i < n; i++) {
        if (arr[i] == candidate)
            count++;
    }

    if (count > n / 2)
        return candidate;
    return -1;
}
int main()
{
    int arr[] = { 1, 1, 1, 1, 2, 3, 4 };
    int n = sizeof(arr) / sizeof(arr[0]);
    int majority = findMajority(arr, n);
    cout << " The majority element is : " << majority;
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;

class GFG
{

  // Function to find majority element
  public static int findMajority(int[] nums)
  {
    int count = 0, candidate = -1;

    // Finding majority candidate
    for (int index = 0; index < nums.length; index++) {
      if (count == 0) {
        candidate = nums[index];
        count = 1;
      }
      else {
        if (nums[index] == candidate)
          count++;
        else
          count--;
      }
    }

    // Checking if majority candidate occurs more than
    // n/2 times
    for (int index = 0; index < nums.length; index++) {
      if (nums[index] == candidate)
        count++;
    }
    if (count > (nums.length / 2))
      return candidate;
    return -1;

    // The last for loop and the if statement step can
    // be skip if a majority element is confirmed to
    // be present in an array just return candidate
    // in that case
  }

  // Driver code
  public static void main(String[] args)
  {
    int arr[] = { 1, 1, 1, 1, 2, 3, 4 };
    int majority = findMajority(arr);
    System.out.println(" The majority element is : "
                       + majority);
  }
}

// This code is contribute by Arnav Sharma
```

## 蟒蛇 3

```
# Python implementation for the above approach

# Function to find majority element
def findMajority(arr, n):
    candidate = -1
    votes = 0

    # Finding majority candidate
    for i in range (n):
        if (votes == 0):
            candidate = arr[i]
            votes = 1
        else:
            if (arr[i] == candidate):
                votes += 1
            else:
                votes -= 1
    count = 0

    # Checking if majority candidate occurs more than n/2
    # times
    for i in range (n):
        if (arr[i] == candidate):
            count += 1

    if (count > n // 2):
        return candidate
    else:
        return -1

# Driver Code

arr = [ 1, 1, 1, 1, 2, 3, 4 ]
n = len(arr)
majority = findMajority(arr, n)
print(" The majority element is :" ,majority)

# This code is contributed by shivanisinghss2110 
```

## C#

```
using System;

class GFG
{

  // Function to find majority element
  public static int findMajority(int[] nums)
  {
    int count = 0, candidate = -1;

    // Finding majority candidate
    for (int index = 0; index < nums.Length; index++) {
      if (count == 0) {
        candidate = nums[index];
        count = 1;
      }
      else {
        if (nums[index] == candidate)
          count++;
        else
          count--;
      }
    }

    // Checking if majority candidate occurs more than
    // n/2 times
    for (int index = 0; index < nums.Length; index++) {
      if (nums[index] == candidate)
        count++;
    }
    if (count > (nums.Length / 2))
      return candidate;
    return -1;

    // The last for loop and the if statement step can
    // be skip if a majority element is confirmed to
    // be present in an array just return candidate
    // in that case
  }

  // Driver code
  public static void Main(String[] args)
  {
    int []arr = { 1, 1, 1, 1, 2, 3, 4 };
    int majority = findMajority(arr);
    Console.Write(" The majority element is : "
                       + majority);
  }
}

// This code is contributed by shivanisinghss2110
```

## java 描述语言

```
<script>
// Function to find majority element
function findMajority(nums)
  {
    var count = 0, candidate = -1;

    // Finding majority candidate
    for (var index = 0; index < nums.length; index++) {
      if (count == 0) {
        candidate = nums[index];
        count = 1;
      }
      else {
        if (nums[index] == candidate)
          count++;
        else
          count--;
      }
    }

    // Checking if majority candidate occurs more than
    // n/2 times
    for (var index = 0; index < nums.length; index++) {
      if (nums[index] == candidate)
        count++;
    }
    if (count > (nums.length / 2))
      return candidate;
    return -1;

    // The last for loop and the if statement step can
    // be skip if a majority element is confirmed to
    // be present in an array just return candidate
    // in that case
  }

// Driver code
    var arr = [ 1, 1, 1, 1, 2, 3, 4 ];
    var majority = findMajority(arr);
    document.write(" The majority element is : "
                       + majority);

// This code is contributed by shivanisinghss2110.

</script>
```

**Output**

```
 The majority element is : 1
```

**时间复杂度:** O(n)(两次通过阵列)
T3】空间复杂度: O(1)