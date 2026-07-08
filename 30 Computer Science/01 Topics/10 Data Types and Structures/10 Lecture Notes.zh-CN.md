---
title: Data Types and Structures 中文讲义
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/10 Data Types and Structures/00 Overview|Data Types and Structures]]"
status: active
tags:
  - computerscience/programming
  - lecture-notes
  - zh-CN
---

# Data Types and Structures 中文讲义

程序作用于数据，而数据被组织的方式决定了程序能做什么。本节涵盖八种伪代码数据类型、把不同类型字段归到同一标识符下的记录、存放多个同类型值的数组、在程序结束后仍能保留的文本文件，以及最初的三种抽象数据类型——栈、队列和链表。这些内容全部在 Paper 2 中考查，因此伪代码写法必须熟练，ADT 的思想也要能讲清道理，而不是死记。

## 来源范围

本讲义对应 CAIE 9618 AS 第 10 节 Data Types and Structures，在 Paper 2 中考查：

- 10.1 Data Types and Records：选用 INTEGER、REAL、CHAR、STRING、BOOLEAN、DATE、ARRAY、FILE；记录的目的；定义、读取和写入记录的伪代码。
- 10.2 Arrays：下标、上界和下界；选择一维或二维数组；声明和处理数组的伪代码；冒泡排序；线性查找。
- 10.3 Files：为什么需要文件；逐行处理文本文件的伪代码。
- 10.4 Introduction to Abstract Data Types（ADT）：ADT 是数据加上一组操作；栈、队列和链表作为 ADT；关键特征及选用理由；用它们添加、编辑、删除数据（不要求写伪代码）；每种如何用数组实现。

## 1. 八种伪代码数据类型

**数据类型**规定了变量能取哪些值，以及哪些运算对它有意义。选型时问两个问题：*允许哪些值？* 和 *需要哪些运算？*。计数用 INTEGER，因为它只能整步地增长；温度用 REAL，因为它有小数部分；一个是 / 否标志用 BOOLEAN，因为只可能有两个值。

| 类型 | 存放 | 示例取值 |
| --- | --- | --- |
| **INTEGER** | 整数（正、负或零）。 | `42` |
| **REAL** | 带小数部分的数（浮点）。 | `3.14` |
| **CHAR** | 单个字符。 | `'A'` |
| **STRING** | 由零个或多个字符组成的序列（文本）。 | `"Hello"` |
| **BOOLEAN** | 真值——只有 `TRUE` 或 `FALSE`。 | `TRUE` |
| **DATE** | 一个日历日期，作为单个逻辑值保存（而不是三个整数）。 | `2026/07/07` |
| **ARRAY** | 一组定长、类型*相同*的值，按下标访问。 | `[5, 7, 9]` |
| **FILE** | 后备存储上的一份数据，程序结束后仍然存在。 | `scores.txt` |

有两对容易混淆。**INTEGER 与 REAL**：当值本质上是整数（计数、下标、绝不可能出现小数的数量）时选 INTEGER，只有当分数确有意义（测量值、允许取整的金额）时才选 REAL。**CHAR 与 STRING**：CHAR 恰好放一个字符，与 `'A'` 比较；STRING 放一串字符，与 `"Apple"` 比较——注意伪代码里两者引号风格不同。DATE 类型之所以重要，是因为它让程序能就日历进行推理（先后、差值），而不必手动比较三个独立的日 / 月 / 年整数。

## 2. 记录

**记录（record）** 是一种结构，它在同一个标识符下存放一组*类型各异的*字段。数组做不到这一点：数组的每个元素类型必须相同，所以一位学生的姓名（STRING）、年龄（INTEGER）、是否缴费（BOOLEAN）没法共用一个数组。记录解决了这个问题——每个字段有自己的类型，但它们作为一个逻辑整体存在，一个 `Pupil` 值同时携带姓名、年龄和标志。

在 CAIE 伪代码里，记录用 `TYPE ... ENDTYPE` 定义，每个字段用 `DECLARE <id> : <type>` 声明。然后正常声明一个该记录类型的变量，用点号访问它的字段。

```pseudocode
TYPE Pupil
    DECLARE Name : STRING
    DECLARE Age  : INTEGER
    DECLARE FeePaid : BOOLEAN
ENDTYPE

DECLARE CurrentPupil : Pupil
```

写入记录就是给每个字段赋值；读取记录就是把每个字段用在表达式或输出里。点号从记录变量中选取字段。

```pseudocode
// 保存数据进记录
CurrentPupil.Name    ← INPUT
CurrentPupil.Age     ← INPUT
CurrentPupil.FeePaid ← INPUT

// 从记录中读取数据
OUTPUT "Name: ", CurrentPupil.Name
OUTPUT "Age:  ", CurrentPupil.Age
```

当一个现实事物拥有多个不同类型的属性、且需要一起流动时，记录就是正确的选择。如果属性类型都相同、又需要很多个，那就改用数组。

## 3. 数组

**数组（array）** 是一种数据结构，存放固定数量的同类型值，通过**下标（index）** 访问。**下界**和**上界**界定合法下标的范围；CAIE 伪代码中下界通常是 `1`，所以声明为 `ARRAY[1:5]` 的数组下标为 `1, 2, 3, 4, 5`，长度为五。把上下界搞错——下界是 `1` 却从 `0` 开始，或读过头一格——是最常见的数组错误。

**一维数组（1D）** 是一列值，适合沿单一轴线排列的数据（一周气温、一班成绩）。**二维数组（2D）** 是由行和列组成的网格，适合沿两条轴线排布的数据（每个班多名学生各有若干成绩、一个棋盘的格子）。数据只有一个逻辑维度时选一维，自然成表时选二维。

```pseudocode
// 一维数组：五个考试分数，下标 1 到 5
DECLARE Marks : ARRAY[1:5] OF INTEGER

// 二维数组：3 个班（行），每班 5 个成绩（列）
DECLARE Grid : ARRAY[1:3, 1:5] OF INTEGER
```

处理数组就是遍历每一个合法下标。一维循环让一个计数器从下界走到上界；二维循环则把一个内层循环（列）嵌套在另一个外层循环（行）里，或反过来。

```pseudocode
// 示例 1——对一维数组所有成绩求和
DECLARE Total : INTEGER
Total ← 0
FOR Index ← 1 TO 5
    Total ← Total + Marks[Index]
NEXT Index
OUTPUT "Total = ", Total
```

```pseudocode
// 示例 2——在一维数组中找最高分
DECLARE MaxMark : INTEGER
MaxMark ← Marks[1]
FOR Index ← 2 TO 5
    IF Marks[Index] > MaxMark
        THEN
            MaxMark ← Marks[Index]
    ENDIF
NEXT Index
OUTPUT "Highest = ", MaxMark
```

```pseudocode
// 示例 3——对二维数组的第 2 列求和（遍历 3 行）
DECLARE ColTotal : INTEGER
ColTotal ← 0
FOR Row ← 1 TO 3
    ColTotal ← ColTotal + Grid[Row, 2]
NEXT Row
OUTPUT "Column 2 total = ", ColTotal
```

套路始终一致：用明确的上下界声明数组，在循环前初始化累加器或"目前最佳值"，然后遍历每个合法下标来更新它。找最大值时务必在循环前先读入第一个元素，这样搜索才有可比较的初值。

## 4. 冒泡排序

**冒泡排序（bubble sort）** 反复比较相邻的元素对，如果顺序错就交换，于是每一趟都会把未排序部分里最大的那个值"冒"到它最终的位置。每过一趟，末尾的已排序区就增长一格；如果某趟一次交换都没发生，就提前结束。它简单但慢——在 $n$ 个元素上大约需要 $O(n^2)$ 次比较。

```pseudocode
// 冒泡排序：把 Marks[1..5] 排成升序
DECLARE Temp : INTEGER
DECLARE Swapped : BOOLEAN

REPEAT
    Swapped ← FALSE
    FOR Index ← 1 TO 4          // 比较相邻对 1-2 ... 4-5
        IF Marks[Index] > Marks[Index + 1]
            THEN
                Temp ← Marks[Index]
                Marks[Index] ← Marks[Index + 1]
                Marks[Index + 1] ← Temp
                Swapped ← TRUE
        ENDIF
    NEXT Index
UNTIL Swapped = FALSE
```

在 `[5, 3, 8, 1]` 上追踪一趟。比较下标 1-2：`5 > 3`，交换 → `[3, 5, 8, 1]`，swapped = TRUE。比较 2-3：`5 > 8`？否。比较 3-4：`8 > 1`，交换 → `[3, 5, 1, 8]`，swapped = TRUE。这一趟结束时，最大值 `8` 已固定在末尾的最终位置。因为发生了交换，再跑一趟：`3 > 5`？否；`5 > 1`，交换 → `[3, 1, 5, 8]`；`5 > 8`？否。又发生了交换，于是第三趟：`3 > 1`，交换 → `[1, 3, 5, 8]`；其余按序比较。最后一趟没有交换，`Swapped` 保持 FALSE，排序停止。内层循环只跑到 `上界 - 1`，因为每次比较同时看 index 和 index + 1；跑到上界就会越界读到末尾之外。

## 5. 线性查找

**线性查找（linear search）** 从下界开始，逐个检查数组元素，直到找到目标或耗尽所有元素。它适用于未排序数据和任何数组类型；最坏情况下的代价是 $O(n)$。要点是：找到目标那一刻就停下；如果循环走完仍未匹配，要如实报告"未找到"。

```pseudocode
// 线性查找：TargetValue 是否存在于 Marks[1..5]？
DECLARE Found : BOOLEAN
DECLARE Index  : INTEGER
DECLARE TargetValue : INTEGER

Found ← FALSE
Index ← 1
TargetValue ← INPUT

WHILE Found = FALSE AND Index <= 5
    IF Marks[Index] = TargetValue
        THEN
            Found ← TRUE
        ELSE
            Index ← Index + 1
    ENDIF
ENDWHILE

IF Found = TRUE
    THEN
        OUTPUT "Found at position ", Index
    ELSE
        OUTPUT "Not found"
ENDIF
```

在 `[5, 3, 8, 1, 7]` 中查找 `7`。下标 1：`5 = 7`？否 → Index 2。下标 2：`3 = 7`？否 → Index 3。下标 3：`8 = 7`？否 → Index 4。下标 4：`1 = 7`？否 → Index 5。下标 5：`7 = 7`？是 → Found = TRUE，停止。输出 "Found at position 5"。如果目标是 `9`，循环会在 Index 变成 `6`（越过上界）时退出，Found 仍为 FALSE，输出 "Not found"。循环条件同时守着两个条件：只有既没找到、又没越界时才继续。

## 6. 文件

程序把数据放在主存（RAM）里，而主存是易失的：程序一结束、或一断电，数据就没了。**文件**因此用于任何需要数据留存的场合——在两次运行之间保存、交给另一个程序、或搬到另一台机器。文件存放在后备存储（磁盘）上，是**非易失的**，所以存下的分数、配置项或结果日志下次还在。

CAIE 伪代码用一组固定的小命令处理**文本文件**——由一行或多行字符组成的文件。文件使用前必须以某种模式（读、写、追加）**打开**；用完要**关闭**，以刷新数据并释放句柄。打开期间，`READFILE` 每次读入一行，`WRITEFILE` 写出一行，`EOF`（end-of-file）测试是否还有输入可读。

| 命令 | 用途 |
| --- | --- |
| `OPENFILE <filename> FOR READ` | 打开已有文件，从头读取。 |
| `OPENFILE <filename> FOR WRITE` | 打开文件从头写入（覆盖已有内容）。 |
| `OPENFILE <filename> FOR APPEND` | 打开文件在末尾追加（保留已有内容）。 |
| `READFILE <filename>, <variable>` | 把下一行读入变量。 |
| `WRITEFILE <filename>, <data>` | 向文件写入一行数据。 |
| `EOF(<filename>)` | 若上一次 READFILE 已到文件末尾，返回 TRUE。 |
| `CLOSEFILE <filename>` | 关闭文件，刷新并释放。 |

读取整个文件的标准模式是 `WHILE NOT EOF(...)` 循环：以读模式打开，然后一行接一行地读取并处理，直到没有内容为止，最后关闭。

```pseudocode
// 示例——逐行读取并打印 pupils.txt，直到文件末尾
DECLARE ThisLine : STRING

OPENFILE "pupils.txt" FOR READ
WHILE NOT EOF("pupils.txt")
    READFILE "pupils.txt", ThisLine
    OUTPUT ThisLine
ENDWHILE
CLOSEFILE "pupils.txt"
```

要新建或替换文件，以 `FOR WRITE` 打开并对每一行用 `WRITEFILE`；要在已有文件后追加而不丢失原内容，则以 `FOR APPEND` 打开。金科玉律是：每一个 `OPENFILE` 都必须配对一个 `CLOSEFILE`，而且 `READFILE` 只能在 `NOT EOF` 为真时调用——读到末尾之外是未定义行为。

## 7. 抽象数据类型（ADT）

**抽象数据类型（ADT）** 是一组数据加上可对这组数据执行的一组操作。*抽象*这个词意味着使用者只关心操作及其行为，而不关心物理布局：栈就是"后进先出"，无论它是用数组还是用链式结构存放。考纲点名的三种 ADT 是栈、队列和链表。

| ADT | 顺序规则 | 关键操作 | 典型用途 |
| --- | --- | --- | --- |
| **栈（stack）** | **LIFO**——后进先出。在同一端（栈顶）加入和移除。 | **压栈 push**（加到栈顶）、**出栈 pop**（从栈顶移除） | 撤销 / 重做、后退按钮历史、调用栈、反转。 |
| **队列（queue）** | **FIFO**——先进先出。在一端（队尾）加入，在另一端（队首）移除。 | **入队 enqueue**（加到队尾）、**出队 dequeue**（从队首移除） | 打印缓冲、任务调度、键盘缓冲区、取号排队。 |
| **链表（linked list）** | 无固定顺序；每个**节点（node）** 存放数据加一个指向下一节点的**指针（pointer）**。 | **插入 insert**、**删除 delete**、沿指针**查找 find** | 大小未知的动态列表、播放列表、撤销日志、邻接表。 |

**如何论证选择**，归结为任务需要的顺序规则。程序的撤销功能应当用**栈**，因为最近一个动作必须最先被撤销——LIFO。打印机队列应当用**队列**，因为任务要按到达顺序送出——FIFO。一个需要频繁在中间插入 / 删除、且大小事先未知的元素列表应当用**链表**，因为节点只需调整指针就能挂上或摘下，而无需像数组那样挪动其后的每个元素。

在 AS 阶段**不要求**为这些结构写伪代码，但必须能描述在其中的添加、编辑和删除。栈：压栈加一个新栈顶元素，出栈移除当前栈顶；你永远只能碰栈顶。队列：入队在队尾加入，出队从队首移除；队首是下一个要离开的。链表：插入一个节点时，先把它的指针指向原来跟在当前节点之后的那个节点，再把当前节点指向新节点；删除时，让前一节点的指针直接指向被删节点*之后*的那个节点，从而绕过它。一个**头指针（head pointer）** 记录链表的起点，一个空指针标记末尾。

### 用数组实现这些 ADT

每种 ADT 都可以在一个普通数组之上搭建，再用一两个额外变量作为指向数组内部位置的指针。所谓"用数组实现"就是这个意思：数组提供存储，一个指针变量实现 ADT 的纪律。

- **用数组实现栈**——声明一个存放数据的数组，外加一个整数**栈顶指针（TopOfStack）**。压栈时在 `TopOfStack` 处写入数据再递增指针；出栈时先递减指针再读取 `Data[TopOfStack]`。两种操作都发生在数组的同一端，这正符合 LIFO。压栈前要对照上下界检查指针（栈满），出栈前也要检查（栈空）。
- **用数组实现队列**——声明一个数组加两个整数：**队首指针（front）** 和**队尾指针（rear）**。入队在队尾指针处写入并推进；出队在队首指针处读取并推进。数据按进入的顺序离开，给出 FIFO。真正的实现会在指针到达末端时把它绕回开头（循环队列），从而重复利用数组空间。
- **用两个数组实现链表**——因为一个节点既需要数据值*又*需要一个指向下一节点的指针，所以用**两个平行数组**：一个存数据（`Data[i]`），另一个存对应的下一指针（`Next[i]`）。遍历链表就是读 `Data[i]`，然后跳到 `i = Next[i]`，直到指针为空。另有一个**头指针**存第一个节点的下标；插入或删除不过是改写 `Next` 数组里的值，`Data` 数组原封不动。

要记住的一点是：ADT 与其数组实现*并不是*一回事。ADT 定义的是行为（LIFO、FIFO、指针串联）；数组只是为这种行为提供存储的一种便捷方式。

## 做题顺序

1. 遇到"选数据类型"题，问允许哪些值、需要哪些运算：计数或下标 → INTEGER；带分数的测量 → REAL；单个符号 → CHAR；文本 → STRING；两态标志 → BOOLEAN；日历值 → DATE；多个同类型值 → ARRAY；持久存储 → FILE。
2. 遇到记录题，在 `TYPE ... ENDTYPE` 内列出各字段及其类型，声明一个该类型的变量，再用点号读取和写入每个字段。
3. 遇到数组题，把上下界写清楚（`ARRAY[1:n]` 或 `ARRAY[1:r, 1:c]`），在循环前初始化累加器或"目前最佳值"，并遍历每个合法下标——绝不超过上界。
4. 遇到冒泡排序题，写 `REPEAT ... UNTIL Swapped = FALSE` 外层循环和跑到 `上界 - 1` 的 `FOR` 内层循环，交换相邻的逆序对；追踪时列出每次比较后的数组。
5. 遇到线性查找题，置 `Found ← FALSE`、`Index` 为下界，在未找到且未越界时循环，退出时明确区分找到和未找到两种情况。
6. 遇到文件题，每个 `OPENFILE` 都配一个 `CLOSEFILE`，按任务选 READ / WRITE / APPEND，并用 `WHILE NOT EOF` 守护 `READFILE`。
7. 遇到 ADT 题，点出顺序规则（LIFO / FIFO / 指针链）和操作，按规则论证选择，再说明数组实现时各保留哪些指针。

## 常见错误

- 该用 INTEGER 时用了 REAL（计数或下标不可能有小数），或该用 REAL 时用了 INTEGER（带小数的测量值）。
- 把 CHAR（单字符 `'A'`）和 STRING（文本 `"Apple"`）搞混。
- 声明数组却忘了上下界，或下界是 `1` 却从 `0` 开始循环，或读过头一格越过上界。
- 冒泡排序的内层循环跑到上界而不是 `上界 - 1`，使最后一次比较读越界。
- 线性查找时忘了找到就停，或循环结束时忘了报告"未找到"。
- 打开文件却不关闭，或未用 `EOF` 守护就调用 `READFILE`。
- 想往文件追加却用了 `FOR WRITE`——它会覆盖。向已有文件追加要用 `FOR APPEND`。
- 把 ADT 当成和它的数组实现一回事。ADT 是*行为*；数组只是*存储*它的一种方式。
- 忘了栈或队列在哪一端操作：栈只在*栈顶*压栈和出栈；队列从*队尾*入队、从*队首*出队。
- 描述链表删除时忘了重指前一节点——被删节点必须通过改写 `Next` 值被绕过。

## 快速自查

如果下面这些问题不看笔记也能答上来，就可以进入下一节。

1. 说出八种伪代码数据类型，并各举一个示例取值。
2. 各举一个理由：何时选 INTEGER 而非 REAL、何时选 REAL 而非 INTEGER。
3. 用示例区分 CHAR 和 STRING。
4. 为一个含三个不同类型字段的记录写 `TYPE ... ENDTYPE`，并写读取一个字段、写入另一个字段的伪代码。
5. 声明一个含五个整数的一维数组和一个 3 行 5 列的二维数组，再对二维数组的第 2 列求和。
6. 为含五个元素的数组写冒泡排序，并在 `[4, 1, 3, 2, 5]` 上追踪一趟。
7. 写一个线性查找，并在 `[4, 1, 3, 2, 5]` 中追踪查找 `3` 的过程。
8. 解释为什么需要文件，并说出三种打开模式，指出哪个覆盖、哪个追加。
9. 写出逐行读取并打印一个文本文件直到文件末尾的伪代码。
10. 用一句话定义 ADT，并分别说出栈、队列、链表的顺序规则和操作。
11. 各用一句话说明：撤销功能为何用栈、打印队列为何用队列、动态学生列表为何用链表。
12. 描述如何用数组实现栈、队列、链表，并说出各自需要的指针变量。

## 关联内容

- [[30 Computer Science/01 Topics/19 Computational Thinking and Problem-solving/00 Overview|Computational Thinking and Problem-solving]] 把这里定义的 ADT 发展成完整算法（压栈、出栈、入队、出队、遍历）。
- [[30 Computer Science/01 Topics/09 Algorithm Design and Problem-solving/00 Overview|Algorithm Design and Problem-solving]] 提供本讲义通篇使用的伪代码记法和追踪习惯。
