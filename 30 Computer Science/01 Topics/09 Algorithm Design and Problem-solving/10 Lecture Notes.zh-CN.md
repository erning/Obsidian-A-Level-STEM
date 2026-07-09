---
title: Algorithm Design and Problem-solving 中文讲义
subject: Computer Science
syllabus: 9618
parent: "[Algorithm Design and Problem-solving](00%20Overview.md)"
status: active
tags:
  - computerscience/programming
  - lecture-notes
  - zh-CN
---

# Algorithm Design and Problem-solving 中文讲义

程序不是凭空敲出来的。在写任何代码之前，必须先理解问题、化简问题、把它拆成小块，再把解法表达成一串没有歧义的步骤。这一节讲的就是完成这件事所需的思维技能（抽象与分解）和表达工具（结构化英语、流程图、伪代码），它们能把一个含糊的问题描述变成计算机能执行的东西。本节在 Paper 2 中考查，答题要用官方伪代码。

## 来源范围

这份讲义对应 CAIE Computer Science 9618 的 AS 第 9 节：

- 9.1 Computational Thinking Skills（抽象与分解）
- 9.2 Algorithms（伪代码、标识符表、三种基本结构、文档化表示法、逐步求精、逻辑语句）

第 9 节在 Paper 2 中考查。

## 1. 抽象

抽象（abstraction）就是把一个现实问题缩减到只留下对求解有用的特征，刻意丢掉其余一切。结果是一个只含必要细节的**抽象模型（abstract model）**。

**为什么需要。** 一个现实问题自带的细节远比程序能处理或应该处理的多。一本图书馆的书有封面颜色、页数、价格和简介，但这些都不能帮系统判断谁借了它、什么时候到期。处理无关细节会浪费内存、掩盖真正的逻辑，还让程序更难设计和测试。

**目的。** 抽象让你把注意力集中在解法真正依赖的数据和行为上，让问题小到能想清楚、能写出来。

**好处。**

- 问题变简单了，因为只剩下相关信息。
- 模型更容易设计、编码和测试。
- 解法可推广：同一个模型适用于任何图书馆，而不只是某一家。
- 无关细节不可能引入 bug，因为它压根没被放进来。

**怎么建立抽象模型。** 先列出关于这个情境的所有已知事实，再划掉对当前问题没有影响的部分。剩下的就是模型。给这些数据项起好名字，就有了标识符表的雏形。

### 例题：图书馆借阅系统

先看现实情境里都有些什么。一本书有书名、作者、ISBN、出版社、出版年、页数、封面颜色、书架位置、类别和价格。一个借阅者有姓名、地址、电话、邮箱、会员号、加入日期、照片和未缴罚金。一次借阅把一本书和一个借阅者关联起来，还有借出日期、到期日期、归还日期和续借次数。

系统要回答的问题很窄：谁借了哪本书，什么时候到期？把没用的细节划掉：

- 书：丢掉出版社、出版年、页数、封面颜色、书架位置、类别、价格、简介，只留一个标识符和书名。
- 借阅者：丢掉地址、电话、邮箱、照片、加入日期，只留一个标识符和姓名。
- 借阅：保留哪本书、哪个借阅者、到期日期，核心模型里丢掉续借次数和归还日期。

抽象模型现在只剩下三小撮数据，正是借阅追踪程序所需要的：

| 实体 | 保留的必要数据 |
|---|---|
| 书（Book） | BookID, Title |
| 借阅者（Borrower） | MemberID, Name |
| 借阅（Loan） | BookID, MemberID, DueDate |

被移除的每一项，都是程序不必存储、不必校验、不必显示的细节。

## 2. 分解

分解（decomposition）就是把一个大问题拆成更小、更好处理的子问题，每个子问题都能单独解决。这些子问题就成了程序的**模块（module）**。在伪代码里，模块要么是**过程（procedure）**——执行一个任务但不返回值，要么是**函数（function）**——执行一个任务并返回一个值。

**为什么有用。** 一个大问题很难整体把握，而一组小的、有名字的任务则不然。每个模块都能单独设计、单独编写、单独测试，而且一个把一件事做好的模块还能在别的程序里复用。

**怎么分解。** 读一遍题目，问自己“这个程序主要得做哪几件事？”把每件事写成一个短语。如果某个短语其实还藏着不止一个任务，就再拆。每个最终任务就是一个模块。

### 例题：学生成绩报告

**题目。** 读入一个学生的姓名和五科成绩，然后输出一份报告，显示平均分、总评等级、是否通过。

把主要任务拆开：

1. 读入学生姓名和五科成绩。
2. 计算五科的平均分。
3. 由平均分确定等级。
4. 输出报告。

每个任务变成一个模块。“计算平均分”和“确定等级”接收输入并产生结果，所以是函数。“读入数据”和“输出报告”要做事但不必返回值，所以是过程（它们读入的数据可以放进主程序共享的变量里）。

| 模块 | 类型 | 职责 |
|---|---|---|
| ReadData | 过程 | INPUT 姓名和五科成绩 |
| CalculateAverage | 函数 | 返回五科平均分 |
| DetermineGrade | 函数 | 由平均分返回等级 |
| PrintReport | 过程 | OUTPUT 报告 |

于是主程序读起来就是按顺序的四个调用，这正是它后面写成伪代码时的样子。

## 3. 算法与标识符表

**算法（algorithm）**是一串有定义的步骤，用来解决一个问题或完成一个任务。要算作算法，这些步骤必须是有限的（会结束）、无歧义的（每步只有一种含义）、有效的（每步都切实可行）。

每个算法都在处理数据，而数据活在**标识符（identifier）**里——给变量和常量起的名字。好的标识符名要有意义、能描述这个值代表什么，所以 `TotalMark` 清楚，`x` 不清楚。算法用到的全部标识符记在一张**标识符表（identifier table）**里，列出每个名字、它的数据类型，以及它的用途说明。这张表写在伪代码之前或旁边，让读者确切知道每个变量装的是什么。

### 例题：“三个数中最大值”的标识符表

题目：输入三个数，输出其中最大的。需要的数据是三个输入，外加一个保存“目前找到的最大值”的变量。

| 标识符 | 数据类型 | 说明 |
|---|---|---|
| `Num1` | REAL | 输入的第一个数 |
| `Num2` | REAL | 输入的第二个数 |
| `Num3` | REAL | 输入的第三个数 |
| `Largest` | REAL | 目前找到的最大值 |

有了这张表，后面的伪代码就能直接用这些名字，不必再解释，因为表里已经说清每个名字的含义。

## 4. 三种基本结构

每个算法都只由三种基本结构组成。再复杂的逻辑，也不过是它们的某种组合。

**顺序（sequence）**——步骤一条接一条、按次序执行。

```pseudocode
Num1 ← 6
Num2 ← 9
Sum ← Num1 + Num2
OUTPUT "Sum is ", Sum
```

**选择（selection）**——根据条件在不同路径之间选择。`IF` 语句处理一两条分支；`CASE OF` 根据单个变量的值从多个分支里选一条。

```pseudocode
// 两路选择
IF Sum >= 10 THEN
    OUTPUT "Large"
ELSE
    OUTPUT "Small"
ENDIF

// 多路选择
CASE OF Grade
    "A" : OUTPUT "Excellent"
    "B" : OUTPUT "Good"
    "C" : OUTPUT "Satisfactory"
    OTHERWISE OUTPUT "Refer"
ENDCASE
```

**循环（iteration）**——把一组步骤重复执行。三种形式对应三种场景。`FOR` 重复已知次数；`WHILE` 在每次重复前测试，可能一次都不执行；`REPEAT` 先执行循环体再测试，所以至少执行一次。

```pseudocode
// 固定次数
FOR Count ← 1 TO 5
    OUTPUT Count
NEXT

// 前置条件循环：可能一次都不执行
INPUT Answer
WHILE Answer <> "stop" DO
    OUTPUT "You said ", Answer
    INPUT Answer
ENDWHILE

// 后置条件循环：至少执行一次
REPEAT
    INPUT Guess
UNTIL Guess = SecretNumber
```

`WHILE` 和 `REPEAT` 的区别在于条件何时测试：`WHILE` 在循环体之前测，`REPEAT` 在之后测。当循环可能根本不需要执行时用 `WHILE`；当循环体至少得执行一次、之后测试才有意义时用 `REPEAT`。

## 5. 同一算法的三种表示法

一个算法可以用三种方式写下来，你必须能在它们之间转换。三者只是形式化程度不同，逻辑完全一样。

- **结构化英语（structured English）** 是按三种基本结构组织的自然语言英语，用缩进体现结构。写得快、非程序员也读得懂，但可能有歧义。
- **流程图（flowchart）** 是一张图。每种步骤用专门的符号，箭头表示执行顺序。一眼能看清控制流，但画起来慢，算法一大就难改。
- **伪代码（pseudocode）** 是一种紧凑的、近似编程语言的记法，但又不是任何一种具体的语言。它是 Paper 2 用的形式，严格遵循 CAIE Pseudocode Guide。

### 流程图符号

| 符号（形状） | 含义 |
|---|---|
| 起止框（圆角矩形，terminator） | 开始或结束 |
| 处理框（矩形，process） | 一个动作：赋值、计算 |
| 判断框（菱形，decision） | 一个条件，分出 Yes / No 两支 |
| 输入输出框（平行四边形，input/output） | 读入数据或写出数据 |
| 流向线（箭头，flow line） | 执行方向 |

### 例题：三个数中最大值的三种写法

题目：输入三个数，输出其中最大的。

**结构化英语。**

1. 输入三个数：Num1、Num2、Num3。
2. 把 Largest 设为 Num1。
3. 如果 Num2 大于 Largest，就把 Largest 设为 Num2。
4. 如果 Num3 大于 Largest，就把 Largest 设为 Num3。
5. 输出 Largest。

**流程图**（从上往下读；括号里注明该框的符号）：

```text
          ( Start )                         ← 起止框
              |
  / INPUT Num1, Num2, Num3 /                ← 输入输出框
              |
         Largest ← Num1                    ← 处理框
              |
      < Num2 > Largest ? >                  ← 判断框
        / Yes        \ No
         |             |
    Largest ← Num2    |
         |_____________|
              |
      < Num3 > Largest ? >                  ← 判断框
        / Yes        \ No
         |             |
    Largest ← Num3    |
         |_____________|
              |
       / OUTPUT Largest /                   ← 输入输出框
              |
          ( End )                           ← 起止框
```

**伪代码。**

```pseudocode
INPUT Num1
INPUT Num2
INPUT Num3
Largest ← Num1
IF Num2 > Largest THEN
    Largest ← Num2
ENDIF
IF Num3 > Largest THEN
    Largest ← Num3
ENDIF
OUTPUT "Largest is ", Largest
```

三种写法描述的是同样的步骤、同样的次序。它们之间的转换只是换表面的记法，不动逻辑：流程图里的每个框对应伪代码里的一行或一块，结构化英语里的每一行也对应同样内容。

## 6. 逐步求精

逐步求精（stepwise refinement）是一种自顶向下的设计方法。先把解法写成几条高层步骤、用大白话表述，然后逐个拿过来，把每条再展开成更细的步骤。不断展开，直到每一步都具体到能直接翻译成伪代码。结果还是同一个算法，只是按越来越细的层次写出来。

规则是逐层推进：不要一边对某个部分直接跳到伪代码，一边让另一部分还是含糊的一句话。要在任何地方深入之前，先把这一层的每一步都求精。

### 例题：全班成绩统计

**题目。** 读入全班的成绩（人数事先不知，输入 -1 作为结束标志），然后输出全班平均分和及格人数（成绩不低于 50 分）。

**第 0 层——主要步骤。**

1. 读入所有成绩。
2. 计算全班平均分。
3. 统计及格人数。
4. 输出结果。

**第 1 层——逐条求精。**

1. 读入所有成绩：反复 INPUT 一个成绩，直到出现结束标志 -1，把每个成绩存进数组并计数。
2. 计算平均分：把数组里所有成绩求和，再除以人数。
3. 统计及格人数：再遍历一遍数组，遇到不低于 50 的就让计数器加一。
4. 输出平均分和及格人数。

**第 2 层——伪代码。**

```pseudocode
DECLARE Mark : ARRAY[1:100] OF REAL
DECLARE Count : INTEGER
DECLARE Index : INTEGER
DECLARE Sum : REAL
DECLARE Average : REAL
DECLARE PassCount : INTEGER
DECLARE ThisMark : REAL

// 1. 读入所有成绩
Count ← 0
INPUT ThisMark
WHILE ThisMark <> -1 DO
    Count ← Count + 1
    Mark[Count] ← ThisMark
    INPUT ThisMark
ENDWHILE

// 2. 计算平均分
Sum ← 0
FOR Index ← 1 TO Count
    Sum ← Sum + Mark[Index]
NEXT
Average ← Sum / Count

// 3. 统计及格人数
PassCount ← 0
FOR Index ← 1 TO Count
    IF Mark[Index] >= 50 THEN
        PassCount ← PassCount + 1
    ENDIF
NEXT

// 4. 输出结果
OUTPUT "Average = ", Average
OUTPUT "Number passed = ", PassCount
```

最终代码里每条注释都对应第 1 层的一个步骤，这正是这套方法的意义：高层结构一直活到成品的程序里。

## 7. 逻辑语句

**逻辑语句（logic statement）**是用比较运算拼起来、再用逻辑运算符 `AND`、`OR`、`NOT` 连接的条件。逻辑语句出现在任何要做决定的地方：`IF` 的条件里、`CASE OF` 的选择里，以及 `WHILE` 和 `REPEAT` 所测试的条件里。

比较用的是熟悉的关系运算符：`=`、`<`、`>`、`<=`、`>=` 和 `<>`（不等于）。逻辑运算符把它们组合起来：

- `AND`：两边都为真时才为真。
- `OR`：至少一边为真时就为真。
- `NOT`：把单个条件取反。

```pseudocode
// 及格要求成绩不低于 50 且出勤率高于 75%
IF Mark >= 50 AND Attendance > 75 THEN
    OUTPUT "Pass"
ELSE
    OUTPUT "Refer"
ENDIF

// 9 点到 17 点之外算加班
IF Hour < 9 OR Hour > 17 THEN
    OUTPUT "Overtime"
ENDIF

// 一直问到输入有效（非无效）为止
REPEAT
    INPUT Age
UNTIL NOT (Age < 0 OR Age > 120)
```

括号的作用和算术里一样重要。`A AND B OR C` 会被读成 `(A AND B) OR C`，这和 `A AND (B OR C)` 不是一回事。条件只要稍微复杂一点，就把括号显式写出来，免得含义被读错。

## 做题顺序

无论哪种算法题，都可以按这个顺序走。

1. 读题，先找出输入、处理、输出。动笔之前先写下来。
2. 确定程序需要什么数据，写出标识符表。
3. 把问题分解成模块，标清哪些是过程、哪些是函数。
4. 先用结构化英语或流程图勾出逻辑，在动手写伪代码之前把控制流理清。
5. 翻译成官方伪代码，用上三种基本结构和赋值箭头 `←`。
6. 用一小组测试数据逐行走查算法，确认输出符合预期。

## 常见错误

- 还没找出输入和输出就开始写伪代码。
- 在抽象模型里塞进无关细节（抽象的意思就是把它丢掉）。
- 把分解出来的步骤弄得不像模块，或者让一个函数干好几件事。
- 选错循环：循环体可能一次都不该执行却用了 `REPEAT`，或次数未知却用了 `FOR`。
- 漏掉 `ENDIF`、`ENDCASE`、`NEXT`、`ENDWHILE`，或者用 `=` 当赋值而不是 `←`。
- 写逻辑语句不加括号，导致 `AND` / `OR` 的分组有歧义。
- 用了 Pseudocode Guide 里没有的记法。

## 快速自查

下面这些问题不用看笔记也能答上来，就可以进入下一节。

1. 说清抽象是什么，并给出一个好处。
2. 给一个记录哪些车位已被占用的停车场建立抽象模型，列出你会保留的必要数据。
3. 过程和函数有什么区别？
4. 把一个“自动售货机”程序分解成四个模块。
5. 给一个把摄氏度转成华氏度的程序写标识符表。
6. 说出三种基本结构的名字，各举一个伪代码例子。
7. 画出起止框、处理框、判断框、输入输出框的流程图符号。
8. 把“找出两个数中较小的一个”分别用结构化英语和伪代码写出来。
9. 把第 0 层的步骤“处理一个姓名列表”求精两层。
10. `A AND B OR C` 为什么需要括号？它有哪两种可能含义？

## 关联内容

- [Computational Thinking and Problem-solving](../19%20Computational%20Thinking%20and%20Problem-solving/00%20Overview.md) 把这些技能推广到查找与排序算法、递归、抽象数据类型和复杂度分析。
- [Programming](../11%20Programming/00%20Overview.md) 把这些设计变成用高级语言写成的真实代码。
- [Pseudocode and Programming Reference](../../04%20Reference/Pseudocode%20and%20Programming%20Reference.md) 是所有伪代码答题的记法参考。
