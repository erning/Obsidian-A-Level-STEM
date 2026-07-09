---
title: Programming 中文讲义
subject: Computer Science
syllabus: 9618
parent: "[Programming](00%20Overview.md)"
status: active
tags:
  - computerscience/programming
  - lecture-notes
  - zh-CN
---

# Programming 中文讲义

本讲义对应 9618 AS 大纲的 **11 Programming（编程）** 部分，在 **Paper 2** 中考查。目标是熟练掌握官方 Pseudocode Guide 记法：能够根据设计写出常量、变量、表达式、控制结构、过程和函数。下面的示例都严格采用该记法，包括赋值箭头 `←`。

## 来源范围

- 大纲 11.1 Programming Basics —— 声明、赋值、表达式、输入/输出、内置函数。
- 大纲 11.2 Constructs —— `IF`、`CASE`、三种循环以及各自适用的场景。
- 大纲 11.3 Structured Programming —— 过程、函数、参数，以及考官期望的术语。

## 1. 常量与变量

**常量**是程序运行期间不会改变的命名值，用 `CONSTANT` 声明一次即可。**变量**是值可以改变的命名存储位置，用 `DECLARE` 声明其名字和类型。两者都是声明语句，告诉读者和编译器这里存在什么。给变量赋值时使用赋值箭头 `←`。

```pseudocode
CONSTANT Pi = 3.14159
CONSTANT MaxTries = 3

DECLARE Radius : REAL
DECLARE Area : REAL
DECLARE Count : INTEGER

Radius ← 5.0
Area ← Pi * Radius * Radius
Count ← 0
```

> 每个变量在使用前都要初始化。读取未初始化的变量是常见的失分点。

## 2. 表达式与运算符

表达式把值和运算符组合起来得到一个结果。运算符的**优先级**决定求值顺序，必要时用括号让意图清晰或覆盖默认优先级。

| 类别 | 运算符 | 说明 |
|------|--------|------|
| 算术 | `+  -  *  /` | `/` 为实数除法 |
| 整数运算 | `DIV  MOD` | `DIV` 取整商，`MOD` 取余数 |
| 关系 | `=  <>  >  <  >=  <=` | 结果为 `TRUE`/`FALSE` |
| 逻辑 | `AND  OR  NOT` | 组合布尔结果 |

上面各行从高到低排列，同行内遵循通常的从左到右规则。`DIV`、`MOD` 和 `*` 优先于 `+`、`-`，它们又优先于关系运算符和逻辑运算符。

```pseudocode
DECLARE Total, N, Remainder : INTEGER
DECLARE Average : REAL
DECLARE Pass : BOOLEAN

Total ← 17
N ← 5
Average ← Total / N          // 3.4，实数除法
Remainder ← Total MOD N      // 2
Pass ← (Total >= 10) AND (Remainder = 2)   // TRUE
```

## 3. 输入与输出

`INPUT` 从键盘读取一个值并存入变量，`OUTPUT` 把值和文本打印到控制台。在 `INPUT` 之前用 `OUTPUT` 给出清晰提示，用户才知道要输入什么。

```pseudocode
OUTPUT "Enter your name: "
INPUT Name
OUTPUT "Hello, ", Name
```

## 4. 内置函数与库例程

可以直接使用内置函数和库例程。Pseudocode Guide 中没有的例程都会在题目里给出定义，**字符串处理函数一定会提供**，所以不要自己发明——按题目给定的来调用并严格遵循其用法。

```pseudocode
DECLARE Index : INTEGER
DECLARE Letter : CHAR

Index ← LENGTH(Name)         // 题目提供的函数
Letter ← UCASE(Name[0])      // 题目提供的函数
```

## 5. 构造

### 5.1 选择 —— 带有 ELSE 和嵌套的 IF

`IF ... THEN ... ELSE ... ENDIF` 在多个备选方案之间做选择。在分支内部嵌套 `IF`，可以依次测试多个条件。

```pseudocode
IF Score >= 80 THEN
    OUTPUT "A"
ELSE
    IF Score >= 60 THEN
        OUTPUT "B"
    ELSE
        OUTPUT "C"
    ENDIF
ENDIF
```

### 5.2 选择 —— CASE

`CASE OF <id>` 根据一个表达式的值进行分发。每条路径在值（或几个值）后跟动作；`OTHERWISE` 子句捕获所有未匹配的情况。

```pseudocode
CASE OF Day
    1    : OUTPUT "Monday"
    2    : OUTPUT "Tuesday"
    3, 4 : OUTPUT "Midweek"
    OTHERWISE OUTPUT "Other"
ENDCASE
```

### 5.3 计数循环 —— FOR

当重复次数事先已知、并由计数器驱动时，使用 `FOR`。计数器依次取从 `v1` 到 `v2`（含）的每个值。

```pseudocode
FOR i ← 1 TO 10
    OUTPUT i, " squared is ", i * i
NEXT i
```

### 5.4 后置条件循环 —— REPEAT

`REPEAT ... UNTIL <cond>` **先执行**循环体，再测试条件；条件为 `FALSE` 时重复，变为 `TRUE` 时停止。循环体至少执行一次。

```pseudocode
REPEAT
    OUTPUT "Enter a positive number: "
    INPUT Value
UNTIL Value > 0
```

### 5.5 前置条件循环 —— WHILE

`WHILE <cond> ... ENDWHILE` 在执行循环体**之前**测试条件，条件为 `TRUE` 时重复。如果一开始条件就为 `FALSE`，循环体一次也不会执行。

```pseudocode
WHILE Total < Target
    Total ← Total + Next
    INPUT Next
ENDWHILE
```

### 5.6 选择循环

| 循环 | 测试时机 | 执行条件 | 最少执行次数 | 适用场景 |
|------|----------|----------|--------------|----------|
| `FOR ... NEXT` | 计数器边界 | 次数事先已知 | 0（当 `v1 > v2`） | 固定的、按计数驱动的重复 |
| `REPEAT ... UNTIL` | 循环体之后 | 条件为 `FALSE` 时重复 | 1 | 循环体必须至少执行一次 |
| `WHILE ... ENDWHILE` | 循环体之前 | 条件为 `TRUE` 时重复 | 0 | 可能需要零次迭代 |

> 次数固定用 `FOR`；可能一次都不执行用 `WHILE`；循环体必须先执行一次再测条件用 `REPEAT`。

## 6. 过程

**过程**是执行某项任务的命名代码块，通过 `CALL` 调用。用过程可以避免重复一段语句，并给一块工作起一个清晰的名字。参数用于把数据传入，可以是**按值传递**（传副本，默认）或**按引用传递**（`BYREF`，过程内的修改会影响调用方的变量）。

```pseudocode
PROCEDURE Swap(BYREF A : INTEGER, BYREF B : INTEGER)
    DECLARE Temp : INTEGER
    Temp ← A
    A ← B
    B ← Temp
ENDPROCEDURE

CALL Swap(X, Y)   // X 和 Y 现在交换了彼此的值
```

`Swap` 必须用 `BYREF`：按值传递只会交换副本，原始变量保持不变。

## 7. 函数

**函数**是通过 `RETURN` **返回单个值**的命名代码块。因为函数会产生一个值，所以它**用在表达式内部**——调用会被它的返回值替换。只要一块代码的目的是计算并返回一个结果，就该用函数而不是过程。

```pseudocode
FUNCTION Larger(A : INTEGER, B : INTEGER) RETURNS INTEGER
    IF A > B THEN
        RETURN A
    ELSE
        RETURN B
    ENDIF
ENDFUNCTION

Biggest ← Larger(Larger(First, Second), Third)   // 用在表达式中
```

这里 `Larger(...)` 会被求值并用结果替换，因此 `Larger(Larger(First, Second), Third)` 能找出三个值中的最大者。

## 8. 术语

| 术语 | 含义 |
|------|------|
| 过程头/函数头 | 第一行：名字、参数，以及（函数的）返回类型 |
| 接口 | 调用方需要知道的全部信息：名字、参数和返回类型 |
| 参数 | 过程头中声明的、用于接收值的变量 |
| 实参 | 在 `CALL` 中实际传入的值 |
| 返回值 | 函数通过 `RETURN` 产生的单个结果 |

## 9. 编写高效的伪代码

- 使用**有意义的标识符** —— 用 `Total` 而不是 `T`，用 `IsValid` 而不是 `f`。
- 让每个代码块只承担**一个明确职责**；如果名字里需要"和"，就拆开。
- **避免重复** —— 把重复出现的代码块提取为过程或函数。
- 使用前先初始化，尽量减少嵌套层数。
- 只为关键步骤写注释，不要解释显而易见的内容。

## 做题顺序

1. 通读设计（流程图或结构化英语），列出输入、输出以及各自需要的数据。
2. 用正确的类型声明常量和变量。
3. 把直线步骤翻译成赋值和 `INPUT`/`OUTPUT`。
4. 用 `IF` 或 `CASE` 处理分支；选择循环时问自己"重复多少次？"和"可能为零次吗？"。
5. 把重复逻辑包成过程，把计算结果包成函数。
6. 用样例值走查一遍，确认每个箭头和条件都正确。

## 常见错误

- 把赋值箭头 `←` 写成 `<-` 或 `=`。
- 在本该用 `=`（比较）的地方用了赋值——伪代码里 `=` 是关系运算符，赋值必须用 `←`。
- 漏掉 `ENDIF`、`ENDCASE`、`NEXT`、`ENDWHILE`、`ENDPROCEDURE`、`ENDFUNCTION`。
- 把应该声明在循环外的变量声明到了循环内部。
- 把函数当语句用，或把过程放进表达式。
- 当调用方的值必须改变时却用了按值传递——记住 `BYREF`。

## 快速自查

- 声明一个 `CONSTANT`、一个 `REAL` 变量，并把该变量乘以 `Pi` 赋给新变量。
- 对 23 和 5 用 `DIV` 和 `MOD` 写一个表达式。
- 把嵌套的 `IF` 改写成针对单个整数值的 `CASE`。
- 为"一直询问直到密码正确"选择最合适的循环。
- 写一个用 `BYREF` 的过程，把一个数翻倍。
- 写一个返回两个 `REAL` 值平均值的函数，并把它用在表达式中。

## 关联内容

- [Further Programming](../20%20Further%20Programming/00%20Overview.md)
- [Algorithm Design and Problem-solving](../09%20Algorithm%20Design%20and%20Problem-solving/00%20Overview.md)
- [Pseudocode and Programming Reference](../../04%20Reference/Pseudocode%20and%20Programming%20Reference.md)
