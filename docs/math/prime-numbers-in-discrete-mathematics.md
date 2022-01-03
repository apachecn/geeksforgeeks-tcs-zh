# 离散数学中的素数

> 原文:[https://www . geesforgeks . org/离散数学中的素数/](https://www.geeksforgeeks.org/prime-numbers-in-discrete-mathematics/)

**概述:**
整数 p > 1 称为[质数](https://www.geeksforgeeks.org/prime-numbers/)，如果 p 的唯一正整数是 1 和 p，则称为质数，不是质数的整数 q > 1 称为复合数。

**例–**
整数 2、3、5、7、11 为质数，整数 4、6、8、9 为复合数。

**定理-1:**
整数 p > 1 是素数当且仅当对于所有整数 a 和 b，p 除 ab 意味着 p 除 a 或 p 除 b

**示例–**
考虑整数 12。现在 12 除 120 = 30×4 但是 12|30 和 12|4。因此，12 不是质数。

**定理-2 :**
每个整数 n > =2 都有一个质因数。

**定理-3 :**
如果 n 是复合整数，那么 n 的质因数不超过√n。

**示例-1 :**
确定以下哪个整数是质数？

```
a) 293 b) 9823
```

**解决方案–**

1.  我们首先找到所有的素数 p，使得 p <sup>2</sup> < = 293。这些素数是 2，3，5，7，11，13 和 17。这些质数都没有除以 293。因此，293 是质数。
2.  我们考虑素数 p，使得 p2< = 9823。这些素数是 2，3，5，7，11，13，17 等。2，3，5，7 都不能除 9823。然而，11 除 9823。因此，9823 不是质数。

**例-2 :**
设 n 为正整数，使得 n <sup>2</sup> -1 为素数。那么 n =？

**解–**
我们可以写，n<sup>2</sup>-1 =(n-1)(n<sup>2</sup>+n+1)。因为 n <sup>3</sup> -1 是素数，要么 n-1 = 1，要么 n <sup>2</sup> +n+1 = 1。现在 n > =1，所以 n <sup>2</sup> +n+1 > 1，即 n <sup>2</sup> +n+1！= 1.因此，我们必须有 n-1 = 1。这意味着 n=2。

**例-3 :**
设 p 为素数，使得 gcd(a，p <sup>3</sup> )=p，gcd(b，p <sup>4</sup> )=p .求 gcd(ab，p <sup>7</sup> )。

**解–**
由给定条件，gcd (a，p <sup>3</sup> )=p .因此，p | a .还有，p <sup>2</sup> |a .(对于如果 p<sup>2</sup>a，那么 gcd(a，p<sup>3</sup>)>= p<sup>2</sup>T32】p，这是矛盾的。)现在 a 可以写成素数幂的乘积。因为 p|a 和 p <sup>2</sup> | a，所以 p 作为因子出现在 a 的素分解中，但是 p <sup>k</sup> ，其中 k > =2，不出现在那个素分解中。类似地，gcd(b，p <sup>4</sup> )=p 意味着 p|b 和 p <sup>2</sup> |b .和以前一样，p 作为一个因子出现在 a 的素分解中，但是 p <sup>k</sup> ，其中 k > =2，不出现在该素分解中。现在接下来是 p <sup>2</sup> |ab 和 p <sup>3</sup> |ab。因此，gcd(b，p <sup>7</sup> ) = p <sup>2</sup> 。

**素性测试算法:**

```
for i: [2,N-1]
  if i divides N
     return "Composite"

return "Prime"        
```

**示例–**
我们举个例子，让算法更高效，36=

<figure class="table">

| 1×36 |
| 2×18 |
| 3×12 |
| (a=4)x(b=9) |
| 6×6 |
| 9×4(重复) |
| 12×3(重复) |
| 18×2(重复) |
| 36×1(重复) |

```
Take the inputs of a and b until,    
 a<=b

 a . b = N
 a . N/a = N
```

**修改算法:**

```
for i : [2,√n]
   if i divides N
     return "Composite"

return "Prime"    
```

## C++

```
// C++ program to check primality of a number
#include <bits/stdc++.h>
using namespace std;

bool is_prime(int n){
   for(int i = 2; i * i <= n; i++){
     if(n % i == 0){
       return false;
       //if the number is composite or not prime.
     }
   }
  return true;
    // number is prime.
}
int main() {

    int n;
    cin >> n;
    cout << is_prime(n) ? "prime" : "composite";
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to check primality of a number

/*package whatever //do not write package name here */

import java.util.*;
class prime{
    public Boolean is_prime(int n){
        for(int i = 2; i * i <= n; i++){
            if(n % i == 0){
                return false;
              //if the number is composite or not prime.
            }
        }
        return true;
      // number is prime.
    }

}

class GFG {
    public static void main (String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        prime ob = new prime();
        System.out.println(ob.is_prime(n) ? "Prime" : "Composite");
    }
}
```

## 蟒蛇 3

```
# Python program to check primality of a number
import math

def is_prime(n):
    for i in range(2, int(math.sqrt(n))):
        if(n % i == 0):
            return False
        # if the number is composite or not prime.

    return True
    #  number is prime.

if __name__ == "__main__":

    n = int(input())
    if is_prime(n):
        print("prime")
    else:
        print("composite")

    # This code is contributed by rakeshsahni
```

## java 描述语言

```
<script>
// JavaScript program to check primality of a number
function is_prime(n)
{
   for(var i = 2; i * i <= n; i++)
   {
     if(n % i == 0){
       return false;

       // if the number is composite or not prime.
     }
   }
  return true;
    // number is prime.
}
    var n;
    document.write(is_prime(n) ? "prime" : "composite");

// This code is contributed by shivanisinghss2110
</script>
```

**求素数的算法:**
在数学中，厄拉多塞的筛子是一种古老的算法，用于寻找任何给定极限内的所有素数。

```
Algorithm Sieve of Eratosthenes is input: an integer n > 1.
output : all prime numbers from 2 through n.

let A be an array of Boolean values, indexed by integers 2 to n,
initially all set to true.

    for i = 2, 3, 4, ..., not exceeding √n do
        if A[i] is true
            for j = i2, i2+i, i2+2i, i2+3i, ..., not exceeding n do
                A[j] := false

    return all i such that A[i] is true.
```

</figure>