---
title: Computational Thinking and Problem-solving 中文讲义
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/19 Computational Thinking and Problem-solving/00 Overview|Computational Thinking and Problem-solving]]"
status: active
tags:
  - computerscience/programming
  - lecture-notes
  - zh-CN
---

# Computational Thinking and Problem-solving 中文讲义

这一节是 A Level 内容，在 AS 第 9 节的基础上加入了标准的查找与排序算法、抽象数据类型的操作、递归，以及用来比较算法的大 O 表示法。AS 讲义只要“描述栈怎么工作”就行，这里你要自己写出查找、排序以及各种 ADT 操作的伪代码，还要能论证一个算法跑得多快、占多少内存。Paper 3 和 Paper 4 都考查本节内容（Paper 4 不考低级语言和声明式语言部分）。

## 来源范围

- 对应 CAIE Computer Science 9618 的 A Level 第 19 节——Computational Thinking and Problem-solving。
- 19.1 Algorithms：线性查找与二分查找；插入排序与冒泡排序；ADT 的查找、插入、删除；图作为一种 ADT；用一个 ADT 实现另一个 ADT；算法的比较与大 O 表示法。
- 19.2 Recursion：递归的本质特征、在编程语言中的表达方式、编写与跟踪递归；编译器如何用栈翻译递归并完成栈展开。
- 在 Paper 3 和 Paper 4 中考查（Paper 4 不考低级语言和声明式语言部分）。

## 1. 线性查找

**线性查找（linear search）** 从下界开始逐个检查数组元素，要么找到目标，要么把元素用完。它没有任何前提条件：数据排不排序都行，也适用于任何类型的数组。它的最坏情况代价是 $O(n)$，因为如果目标在最后或根本不存在，每个元素都要查一遍。

写它的纪律是：一找到就停；循环结束时若仍没匹配，就如实报告“未找到”。

```pseudocode
// 线性查找：TargetValue 是否出现在 Data[1..Upper] 中？
DECLARE Found : BOOLEAN
DECLARE Index : INTEGER

Found ← FALSE
Index ← 1

WHILE Found = FALSE AND Index <= Upper
    IF Data[Index] = TargetValue THEN
        Found ← TRUE
    ELSE
        Index ← Index + 1
    ENDIF
ENDWHILE

IF Found = TRUE THEN
    OUTPUT "Found at position ", Index
ELSE
    OUTPUT "Not found"
ENDIF
```

在 `Data = [5, 3, 8, 1, 7]`（`Upper = 5`）中查找 `7`。`Index = 1`：`5 = 7`？否 → `Index = 2`。`Index = 2`：`3 = 7`？否 → `Index = 3`。`Index = 3`：`8 = 7`？否 → `Index = 4`。`Index = 4`：`1 = 7`？否 → `Index = 5`。`Index = 5`：`7 = 7`？是 → `Found = TRUE`，循环结束。输出 "Found at position 5"。如果目标是 `9`，循环会在 `Index` 变成 `6`（越过上界）时结束，此时 `Found` 仍为 FALSE，输出 "Not found"。

## 2. 二分查找

**二分查找（binary search）** 利用有序数据的特点。每一步它把目标和**中间**元素比较，扔掉不可能包含目标的那一半，在剩下的一半里继续，直到找到或范围为空。

**二分查找的前提条件。** 三条都必须满足：

1. 数据是**已排序**的（升序或降序，保持一致）。
2. 数据支持按索引 $O(1)$ **直接访问**（数组可以，普通链表不行）。
3. 元素之间能用一致的次序关系**比较大小**。

如果数据未排序，二分查找可能给出错误答案，或者漏掉实际存在的元素。

```pseudocode
// 二分查找：TargetValue 是否出现在有序的 Data[1..Upper] 中？
DECLARE Found : BOOLEAN
DECLARE Lower : INTEGER
DECLARE Higher : INTEGER
DECLARE Mid : INTEGER

Found ← FALSE
Lower ← 1
Higher ← Upper

WHILE Found = FALSE AND Lower <= Higher
    Mid ← (Lower + Higher) DIV 2
    IF Data[Mid] = TargetValue THEN
        Found ← TRUE
    ELSE
        IF Data[Mid] < TargetValue THEN
            Lower ← Mid + 1      // 目标在上半部分
        ELSE
            Higher ← Mid - 1     // 目标在下半部分
        ENDIF
    ENDIF
ENDWHILE

IF Found = TRUE THEN
    OUTPUT "Found at position ", Mid
ELSE
    OUTPUT "Not found"
ENDIF
```

在有序数组 `Data = [1, 3, 5, 7, 9]`（`Upper = 5`）中查找 `7`。`Lower = 1, Higher = 5`。`Mid = 3`：`Data[3] = 5`，`5 < 7` → 在上半部分找，`Lower = 4`。`Mid = 4`：`Data[4] = 7`，命中 → `Found = TRUE`。输出 "Found at position 4"。只比较了两次；线性查找要比较五次。

**性能如何随数据量变化。** 每次比较都把查找范围砍一半，所以比较次数随 $n$ 按对数增长。数据量翻倍，最坏情况下只多一次比较。下表列出几个规模的最坏比较次数。

| 数据量 $n$ | 线性查找 $O(n)$ | 二分查找 $O(\log_2 n)$ |
|---|---|---|
| 8 | 8 | 3 |
| 1 000 | 1 000 | 10 |
| 1 000 000 | 1 000 000 | 20 |

$n$ 很小时差别不大；对于大型有序数据集，二分查找明显快得多。代价是前提条件——数据必须先排好序，而这本身就要花时间。

## 3. 冒泡排序与插入排序

两者都是简单的 $O(n^2)$ 排序，实际运行时间不仅取决于数据量，还取决于数据的**初始顺序**。

### 冒泡排序

**冒泡排序（bubble sort）** 反复比较相邻元素对，顺序错了就交换，于是每一趟都会把未排序部分里最大的值“冒泡”到正确位置。某一趟没有发生交换时，它就能提前停止——这也让它能识别已经有序的数组。

```pseudocode
// 冒泡排序：把 Data[1..Upper] 排成升序
DECLARE Temp : INTEGER
DECLARE Swapped : BOOLEAN
DECLARE Index : INTEGER

REPEAT
    Swapped ← FALSE
    FOR Index ← 1 TO Upper - 1
        IF Data[Index] > Data[Index + 1] THEN
            Temp ← Data[Index]
            Data[Index] ← Data[Index + 1]
            Data[Index + 1] ← Temp
            Swapped ← TRUE
        ENDIF
    NEXT Index
UNTIL Swapped = FALSE
```

在 `[5, 3, 8, 1]`（`Upper = 4`）上跟踪一趟。第 1–2 对：`5 > 3`，交换 → `[3, 5, 8, 1]`，`Swapped = TRUE`。第 2–3 对：`5 > 8`？否。第 3–4 对：`8 > 1`，交换 → `[3, 5, 1, 8]`，`Swapped = TRUE`。这一趟结束时最大的值 `8` 已固定在末尾。内层循环跑到 `Upper - 1`，因为每次比较都要读索引和索引 + 1 两个位置。

### 插入排序

**插入排序（insertion sort）** 每次取下一个未排序元素，把它向左移过所有比它大的已排序元素，插到正确位置。被挪的已排序元素各向右移一位腾出空位。

```pseudocode
// 插入排序：把 Data[1..Upper] 排成升序
DECLARE CurrentItem : INTEGER
DECLARE CurrentPos : INTEGER
DECLARE Index : INTEGER

FOR Index ← 2 TO Upper
    CurrentItem ← Data[Index]
    CurrentPos ← Index
    WHILE CurrentPos > 1 AND Data[CurrentPos - 1] > CurrentItem
        Data[CurrentPos] ← Data[CurrentPos - 1]   // 把较大者右移
        CurrentPos ← CurrentPos - 1
    ENDWHILE
    Data[CurrentPos] ← CurrentItem
NEXT Index
```

在 `[3, 5, 8, 1]` 上跟踪 `Index = 4`（那个 `1`）这一步。`CurrentItem = 1`，`CurrentPos = 4`。`Data[3] = 8 > 1` → 把 `8` 右移 → `[3, 5, 8, 8]`，`CurrentPos = 3`。`Data[2] = 5 > 1` → 把 `5` 右移 → `[3, 5, 5, 8]`，`CurrentPos = 2`。`Data[1] = 3 > 1` → 把 `3` 右移 → `[3, 3, 5, 8]`，`CurrentPos = 1`。循环停止（`CurrentPos = 1`）。把 `1` 放到位置 1 → `[1, 3, 5, 8]`。

### 性能如何取决于初始顺序

| 排序 | 最好情况 | 最坏情况 | 平均 |
|---|---|---|---|
| 冒泡 | 已有序：$O(n)$（一趟，无交换） | 逆序：$O(n^2)$ | $O(n^2)$ |
| 插入 | 已有序：$O(n)$（无移动） | 逆序：$O(n^2)$ | $O(n^2)$ |

两者在逆序数据上都退化到 $O(n^2)$，在几乎有序的数据上都接近线性，因为每一趟几乎不做活。实践中插入排序通常比冒泡排序略快，因为它直接搬移元素，不必经历多趟交换。

## 4. 大 O 表示法

**大 O 表示法（Big O notation）** 描述算法对某种资源（时间或内存）的使用量如何随输入规模 $n$ 增长，忽略常数因子和低阶项。它给出的是**增长阶**——曲线的形状，而不是精确计数。对于足够大的 $n$，$O(n^2)$ 的算法总会输给 $O(n \log n)$ 的算法，哪怕 $O(n^2)$ 那边的常数很小。

- **时间复杂度（time complexity）** 是操作次数随 $n$ 的增长。
- **空间复杂度（space complexity）** 是额外内存量随 $n$ 的增长。

说复杂度时，除非另有说明，一律给最坏情况，并从循环结构里给出依据：对 $n$ 个元素走一遍是 $O(n)$；嵌套两层遍历是 $O(n^2)$；每步把范围砍半是 $O(\log n)$。

### 复杂度对比

| 算法 | 时间（最好） | 时间（平均） | 时间（最坏） | 空间 |
|---|---|---|---|---|
| 线性查找 | $O(1)$ | $O(n)$ | $O(n)$ | $O(1)$ |
| 二分查找 | $O(1)$ | $O(\log n)$ | $O(\log n)$ | $O(1)$ |
| 冒泡排序 | $O(n)$ | $O(n^2)$ | $O(n^2)$ | $O(1)$ |
| 插入排序 | $O(n)$ | $O(n^2)$ | $O(n^2)$ | $O(1)$ |

这四个算法都只用固定量的额外内存（$O(1)$ 空间），因为它们直接在数组上原地操作。两种查找的最好情况是 $O(1)$，因为目标可能正好落在第一个被检查的位置。

## 5. ADT 操作

**抽象数据类型（ADT）** 是数据加上一组被定义好的操作的集合；使用者只关心操作及其行为，不关心存储方式。A Level 要求你为下面的操作写出伪代码。

| 结构 | 查找 | 插入 | 删除 |
|---|---|---|---|
| 链表 | 从 head 沿指针遍历 | 把新节点链入 | 重接指针绕过某节点 |
| 二叉树 | 比较后往左或往右走 | 挂在某个空子节点位置 | （不要求） |
| 栈 | （不适用） | 压入栈顶 | 从栈顶弹出 |
| 队列 | （不适用） | 从队尾入队 | 从队头出队 |

节点画成一个记录，含一个数据值外加一个指针（链表）或两个子指针（二叉树）。**头指针（head pointer）** 记录链表从哪里开始，**空指针（null pointer）** 标记链表结尾或空的子节点。

### 在链表中查找

```pseudocode
// 查找持有 TargetValue 的节点；返回位置或 0
DECLARE CurrentPointer : POINTER
DECLARE Found : BOOLEAN

Found ← FALSE
CurrentPointer ← Head

WHILE Found = FALSE AND CurrentPointer <> NullPointer
    IF CurrentPointer.Data = TargetValue THEN
        Found ← TRUE
    ELSE
        CurrentPointer ← CurrentPointer.Next
    ENDIF
ENDWHILE

IF Found = TRUE THEN
    OUTPUT "Found"
ELSE
    OUTPUT "Not found"
ENDIF
```

### 入栈（push）

```pseudocode
// 把 NewValue 压入栈（LIFO：在栈顶加入）
IF TopPointer = MaxSize THEN
    OUTPUT "Stack overflow"
ELSE
    TopPointer ← TopPointer + 1
    Stack[TopPointer] ← NewValue
ENDIF
```

### 入队（enqueue）

```pseudocode
// 把 NewValue 入队（FIFO：在队尾加入）
IF NumberOfItems = MaxSize THEN
    OUTPUT "Queue full"
ELSE
    RearPointer ← (RearPointer MOD MaxSize) + 1   // 循环回绕
    Queue[RearPointer] ← NewValue
    NumberOfItems ← NumberOfItems + 1
ENDIF
```

### 在链表中插入（在某节点之后）

```pseudocode
// 在 CurrentPointer 之后插入持有 NewValue 的新节点
NewNode.Data ← NewValue
NewNode.Next ← CurrentPointer.Next
CurrentPointer.Next ← NewNode
```

新节点的 `Next` 先指向原本跟在 `CurrentPointer` 后面的节点，再把 `CurrentPointer.Next` 重指向新节点。要在头部插入，就设 `NewNode.Next ← Head`，再 `Head ← NewNode`。

### 在二叉树中插入

```pseudocode
// 把 NewValue 插入二叉搜索树
DECLARE CurrentPointer : POINTER
DECLARE Inserted : BOOLEAN

IF Root = NullPointer THEN
    Root.Data ← NewValue
    Root.Left ← NullPointer
    Root.Right ← NullPointer
ELSE
    CurrentPointer ← Root
    Inserted ← FALSE
    WHILE Inserted = FALSE
        IF NewValue < CurrentPointer.Data THEN
            IF CurrentPointer.Left = NullPointer THEN
                CurrentPointer.Left ← NewNode
                NewNode.Data ← NewValue
                NewNode.Left ← NullPointer
                NewNode.Right ← NullPointer
                Inserted ← TRUE
            ELSE
                CurrentPointer ← CurrentPointer.Left
            ENDIF
        ELSE
            IF CurrentPointer.Right = NullPointer THEN
                CurrentPointer.Right ← NewNode
                NewNode.Data ← NewValue
                NewNode.Left ← NullPointer
                NewNode.Right ← NullPointer
                Inserted ← TRUE
            ELSE
                CurrentPointer ← CurrentPointer.Right
            ENDIF
        ENDIF
    ENDWHILE
ENDIF
```

### 出栈（pop）

```pseudocode
// 从栈顶弹出一个值（LIFO：从栈顶移除）
IF TopPointer = 0 THEN
    OUTPUT "Stack underflow"
ELSE
    PoppedValue ← Stack[TopPointer]
    TopPointer ← TopPointer - 1
ENDIF
```

### 出队（dequeue）

```pseudocode
// 从队头取出下一个值（FIFO：从队头移除）
IF NumberOfItems = 0 THEN
    OUTPUT "Queue empty"
ELSE
    DequeuedValue ← Queue[FrontPointer]
    FrontPointer ← (FrontPointer MOD MaxSize) + 1   // 循环回绕
    NumberOfItems ← NumberOfItems - 1
ENDIF
```

### 从链表中删除

```pseudocode
// 删除持有 TargetValue 的节点（用 PreviousPointer 跟在后面）
DECLARE CurrentPointer : POINTER
DECLARE PreviousPointer : POINTER
DECLARE Found : BOOLEAN

Found ← FALSE
CurrentPointer ← Head
PreviousPointer ← NullPointer

WHILE Found = FALSE AND CurrentPointer <> NullPointer
    IF CurrentPointer.Data = TargetValue THEN
        Found ← TRUE
    ELSE
        PreviousPointer ← CurrentPointer
        CurrentPointer ← CurrentPointer.Next
    ENDIF
ENDWHILE

IF Found = TRUE THEN
    IF PreviousPointer = NullPointer THEN
        Head ← CurrentPointer.Next          // 删除头节点
    ELSE
        PreviousPointer.Next ← CurrentPointer.Next   // 绕过该节点
    ENDIF
ENDIF
```

要删的节点被绕过：前一节点的 `Next` 直接重指向被删节点的下一个节点。删除头节点是特例，把 `Head` 往后挪一位即可。

## 6. 图作为一种 ADT

**图（graph）** 是一种抽象数据类型，由一组**顶点（vertex）** 和一组连接顶点对的**边（edge）** 构成。它的关键特征是：

- **顶点** 持有值；**边** 刻画两个顶点之间的关系。
- 边可以是**有向**的（单向）或**无向**的（双向）。
- 边可以带**权值**（代价、距离、容量），这就成了**带权图**。
- 图**没有固定的入口**，也**没有固定的遍历顺序**；和树不同，它可能含环，任意顶点都能连到任意其他顶点。

**为一个情境论证使用图。** 只要问题本质上关乎事物之间的*连接*或*路径*，而非一个序列或一个层级，就该用图。公路或铁路网是图：城镇是顶点，公路是带权边，任务（最短路径）若没有连接结构就毫无意义。社交网络是图：人是顶点，友谊是无向边。网页及其超链接构成有向图。二叉搜索树或数组刻画不了这些，因为它们没有唯一根，也没有固定的父子次序——这些数据是网络。不要求你为图结构写代码，只要能描述它并论证其用途。

## 7. 用内置类型或其他 ADT 实现 ADT

ADT 定义的是行为，背后的存储是另一回事。因为 ADT 只对外暴露操作，一个 ADT 可以**实现于另一个 ADT 之上**，也可以直接实现于数组、记录这样的内置类型之上。承担实现的结构只要遵守那些操作和次序规则即可。

| ADT | 可由什么实现 | 为什么可行 |
|---|---|---|
| **栈** | 一维数组，或链表 | 两者都能在一端增删（LIFO）。 |
| **队列** | 一维数组（循环），或链表 | 两者都能在一端加、另一端删（FIFO）。 |
| **链表** | 两个并列数组（数据 + 下一指针），或记录的动态数组 | `Next` 值重建了指针链。 |
| **字典** | 哈希表，或（键, 值）记录数组，或二叉搜索树 | 通过哈希、查找或比较把键映射到值。 |
| **二叉树** | 一维数组（`Data[i]`，子节点在 `2i` 和 `2i+1`），或带两个子指针的链式记录 | 既可以按位置存节点，也可以用指针串起来。 |

要点是灵活性：如果你已经有了一个能用的链表，只要总在头部增删就能搭出一个栈，不必再写新的存储代码。如果手里只有数组，选对指针方案照样能搭出上面五种 ADT 中的任意一种。

## 8. 递归

**递归（recursion）** 是一个子程序（函数或过程）为了求解同一问题的更小实例而调用自身。它的本质特征有三条：

1. **基线情形（base case）**——一个条件，触发后直接返回值、不再递归调用。没有它，子程序永不停止。
2. **递归情形（recursive case）**——子程序用一个更小或更简单的参数调用自身。
3. **收敛（convergence）**——每一次递归调用都必须向基线情形靠近，从而保证调用链一定终止。

如果一个子程序调用自身却永远不向基线情形靠近，它就会无限递归，调用栈溢出。

**在编程语言中如何表达。** 递归函数和别的函数写法完全一样；递归只是一个 `IF`：要么返回基线值，要么返回 `f(更小参数)`。语言提供机制——每次调用在调用栈上获得自己的一套局部变量和参数，结果在栈展开过程中传回。

### 例题：阶乘

$$n! = n \times (n-1)!, \quad 0! = 1$$

```pseudocode
FUNCTION Factorial(N : INTEGER) RETURNS INTEGER
    IF N = 0 THEN
        RETURN 1                    // 基线情形
    ELSE
        RETURN N * Factorial(N - 1) // 递归情形
    ENDIF
ENDFUNCTION
```

跟踪 `Factorial(3)` 的调用栈。每次调用压入一个栈帧并等待它发起的调用返回；然后栈按相反顺序逐帧展开。

```text
调用 Factorial(3)
  N = 3，非基线，需要 3 * Factorial(2)              [压入帧 3]
    调用 Factorial(2)
      N = 2，非基线，需要 2 * Factorial(1)          [压入帧 2]
        调用 Factorial(1)
          N = 1，非基线，需要 1 * Factorial(0)      [压入帧 1]
            调用 Factorial(0)
              N = 0，基线，RETURN 1                 [帧 0 返回]
          1 * 1 = 1，RETURN 1                       [帧 1 栈展开]
      2 * 1 = 2，RETURN 2                           [帧 2 栈展开]
  3 * 2 = 6，RETURN 6                               [帧 3 栈展开]
结果：6
```

注意栈在 `Factorial(0)` 处最深，随后每个帧乘完并返回，栈逐渐收缩。

### 什么时候适合用递归

递归适合那些定义本身天然自相似的问题：树和图的遍历（一棵子树本身也是树）、分治排序与查找（在每一半上继续做）、以及阶乘、斐波那契、最大公约数这类数学定义。当递归版本比带显式栈的迭代循环明显更短、更贴近问题定义时，用递归就划算。当递归深度可能很大（栈溢出风险），或者一个简单循环就能办妥同一件事时，递归就不划算，因为每次调用都要花一个栈帧的内存。

## 9. 编译器如何翻译递归

编译器不需要什么特殊的“递归”指令；它用的就是每次子程序调用都在用的普通**调用栈**。调用一个函数时，编译器生成的代码会：

1. 求出实参的值。
2. **压入一个栈帧**，含返回地址、参数，以及函数的局部变量。
3. 跳转到该函数的代码。

对递归调用而言，这一过程一遍遍重复：每次调用都获得*自己的*栈帧，*自己的* `N` 副本，所以一帧里的 `N` 不会被用到另一个 `N` 的递归调用所干扰。递归越深，栈帧越积越多。

当某个栈帧终于命中基线情形并返回时，返回值被传回发起调用的那一帧，然后该帧被**弹出**。控制权回到发起调用的栈帧，从它当初停下的地方继续。这种按相反顺序逐帧弹出的过程叫做**栈展开（unwinding，回溯）**。所以 `RETURN N * Factorial(N - 1)` 的意思是：调用 `Factorial(N - 1)`，压入一个栈帧并等待；等它返回后，把结果乘以 `N`，再返回*那个值*。栈正是让每次调用都能记住自己停在哪、拿到结果后该干什么的机制。

## 做题顺序

1. 查找题先看数据是否有序：有序且支持直接访问就用二分查找，否则用线性查找。
2. 排序题选定插入或冒泡后，先在纸上跟踪一整趟，每次比较后列出数组，再动手写伪代码。
3. 大 O 题数嵌套循环：$k$ 层嵌套遍历 $n$ 给 $O(n^k)$；每次砍半的模式给 $O(\log n)$。
4. ADT 操作题先说清次序规则（LIFO、FIFO、指针链、BST 比较），画出操作前后的指针状态，再照图写伪代码。
5. 递归题先写基线情形，再写递归情形，然后跟踪调用栈一层层压下去、再在栈展开过程中一层层传回结果。

## 常见错误

- 对未排序数据用二分查找，或对没有直接访问的结构（普通链表）用二分查找。
- 冒泡排序的内层循环跑到上界而不是 `Upper - 1`，最后那次比较越界。
- 冒泡排序漏掉 `Swapped` 标志，导致即使已有序也要跑完全部趟数。
- 搞错栈或队列用哪一端：栈只在栈顶压入和弹出；队列从队尾入队、从队头出队。
- 写递归子程序时没有基线情形，或递归情形不向基线情形收敛。
- 跟踪递归时只往下走：必须还要把栈解开来，把结果一层层乘回去。
- 把 ADT 等同于它的某一种实现。ADT 是行为；数组或链表只是存储它的一种方式。
- 把大 O 说成操作次数的精确计数，而不是增长阶。

## 快速自查

下面这些问题不用看笔记也能答上来，就可以进入下一节。

1. 说出使用二分查找前必须满足的三个条件。
2. 写一个线性查找，并跟踪它在 `[2, 7, 4, 9]` 中查找 `4` 的过程。
3. 写一个二分查找，并跟踪它在有序的 `[1, 3, 5, 7, 9]` 中查找 `7` 的过程。
4. 二分查找在 1 000 项上最坏要比较几次？1 000 000 项呢？
5. 写一个冒泡排序和一个插入排序，并说出各自的最好和最坏情况。
6. 在 `[5, 3, 8, 1]` 上跟踪一趟冒泡排序。
7. 用一张对比表给出这四个算法的时间和空间复杂度。
8. 写出在链表中查找一个值、以及在某个节点之后插入一个新节点的伪代码。
9. 写出 push、pop、enqueue、dequeue 的伪代码，含溢出/下溢检查。
10. 描述图的关键特征，并论证为什么公路网适合用图。
11. 对栈、队列、链表、字典、二叉树各举一个可用来实现它的结构。
12. 说出递归的三个本质特征，并在调用栈上跟踪 `Factorial(3)`。
13. 解释编译器为每次递归调用往栈里压了什么，“栈展开（unwinding）”又是什么意思。

## 关联内容

- [[30 Computer Science/01 Topics/09 Algorithm Design and Problem-solving/00 Overview|Algorithm Design and Problem-solving]] 是本节所扩展的 AS 基础——抽象、分解、三种基本结构以及伪代码记法都来自那里。
- [[30 Computer Science/01 Topics/10 Data Types and Structures/00 Overview|Data Types and Structures]] 定义了那些 ADT（栈、队列、链表）及其数组实现；本节把它们的操作写成完整算法。
