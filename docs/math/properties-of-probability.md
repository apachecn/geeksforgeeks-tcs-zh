# 概率的性质

> 原文:[https://www.geeksforgeeks.org/properties-of-probability/](https://www.geeksforgeeks.org/properties-of-probability/)

概率是数学的一个分支，它规定了一个事件发生的可能性。[概率](https://www.geeksforgeeks.org/mathematics-probability/)的值在 0 到 1 之间。零(0)表示不可能发生的事件，一(1)表示肯定会发生。下面提到了概率的一些性质

## 概率的性质

#### **1。事件的概率可以定义为**事件的**有利结果数除以**事件的可能结果总数**。**

> 概率(事件)=(事件的有利结果数)/(可能结果的总数)

**例:**抛硬币得到尾巴的概率是多少？

**解决方案:**

```
Number of Favorable Outcomes- {Tail} = 1
Total Number of possible outcomes- {Head, Tail} - 2
Probability of getting Tail= 1/2 = 0.5
```

#### **2。确定/确定**事件**的概率为 1。**

**例:**掷骰子得到 1 到 6 之间的数的概率是多少？

**解:**T0】

#### **3。不可能事件的概率为零(0)。**

**例:**掷骰子得到大于 6 的数的概率是多少？

**解:**T0】

#### **4。事件发生的概率总是在 0 和 1 之间。它总是积极的。**

> 0 <=概率(事件)< = 1

**例:**我们可以注意到在以上所有的例子中概率总是在 0 & 1 之间。

#### **5。如果 A 和 B 是 2 个事件****被认为是互斥事件，那么 P(AUB) = P(A) + P(B)。**

**<u>注意:</u>** 当 if 2 事件不能同时发生时，两个事件是互斥的。

**例:**抛硬币时获得头尾的概率属于互斥事件。

**解:**T0】

#### **6。基本事件是只有一个结果的事件。这些事件也被称为原子事件或样本**点**。**实验中这些基本事件的概率之和**总是 1。**

**例:**当我们抛硬币时，可能的结果是正面或反面。这些单个事件，即只有样本空间的头部或尾部，被称为基本事件。

**解:**T0】

#### **7。互补事件的概率之和为 1。**

> P(A)+P(A’= 1

**例:**抛硬币时，获得领先的概率是 1/2，获得领先的互补事件是获得尾巴，所以获得尾巴的概率是 1/2。

**解:**T0】

#### **8。如果甲和乙是两个事件****不是互斥事件，那么**

*   **p(aub)= p(a)+p(b)-p(a∨t1】**
*   **p(a-b)= p(a)+p(b)-p(aub)**

**<u>注:</u>** 2 个事件至少有一个共同结局时，就说是互不排斥的。

**例:**骰子滚动时得到偶数或小于 4 的概率是多少？

**解:**

```
Favorable outcomes of getting even number ={2,4,6}
Favorable outcomes of getting number<4 ={1,2,3}
So, there is only 1 common outcome between two events so these two events are not mutually exclusive.
```

```
So, we can find P(Even U Number<4)= P(Even) + P(Number<4) - P(Even ∩ Number<4)

P(Even)=3/6=1/2
P(Number<4)=3/6=1/2
P(Even ∩ Number<4)=1/6    (Common element)
P(Even U Number<4)=(1/2) +(1/2)-(1/6)=1-(1/6)=0.83
```

#### 9.如果 E <sub>1</sub> ，E <sub>2</sub> ，E <sub>3</sub> ，E <sub>4</sub> ，E <sub>5</sub> ，……E <sub>N</sub> 是互斥事件，那么概率(E<sub>1</sub>UE<sub>2</sub>UE<sub>3</sub>UE<sub>4</sub>UE<sub>5</sub>U……UE<sub>N【N+P(E <sub>N</sub> )。</sub>

**例:**骰子滚动时得到 1 或 2 或 3 个数的概率是多少。

**解:**T0】

**所以，A、B、C 是互斥事件。**

根据上述概率规则-**P(A U B U C)= P(A)+P(B)+P(C)**

```
P(A)=1/6
P(B)=1/6
P(C)=1/6
P(A U B U C)=(1/6)+(1/6)+(1/6)=3/6=1/2
```

这些是概率最基本的属性。