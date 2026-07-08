---
title: Further Programming 中文讲义
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/20 Further Programming/00 Overview|Further Programming]]"
status: active
tags:
  - computerscience/programming
  - lecture-notes
  - zh-CN
---

# Further Programming 中文讲义

本讲义对应 9618 A Level 大纲的 **20 Further Programming（进一步编程）** 部分。该主题在 AS 11 的基础上扩展为四种编程范式（低级语言、命令式、面向对象、声明式），以及 Paper 4 在你选定语言（Java、Visual Basic .NET 或 Python）中考查的文件处理和异常处理技能。低级语言和声明式编程只在 Paper 3 理论中考查，其余内容在实践题中考查。

## 来源范围

- 大纲 20.1 Programming Paradigms —— 低级语言、命令式/过程式、面向对象、声明式。
- 大纲 20.2 File Processing and Exception Handling —— 对串行、顺序、随机文件的操作；用 Java、Visual Basic .NET 或 Python 程序代码进行异常处理。
- Paper 3（理论，全部范式）与 Paper 4（实践；不含低级语言和声明式）。

## 1. 编程范式

**编程范式**是一种构建程序的风格或思维方式——它把哪些概念、抽象和构造视为基本要素。同一个问题可以用多种范式解决，每种范式都会让某些事情变简单、另一些变困难。理解各自的特征，才能正确选择并读懂用任何范式写出的代码。

| 范式 | 核心思想 | 状态与控制 | 适用场景 |
|------|----------|------------|----------|
| 低级语言 | 针对特定 CPU 的指令；一行对应一条机器指令 | 直接控制寄存器/内存 | 设备驱动、嵌入式代码、寻址方式考题 |
| 命令式/过程式 | 一连串语句通过变量改变程序状态；用过程/函数组织 | 显式的、一步步的 | 大多数 Paper 4 任务；控制流清晰的算法 |
| 面向对象 | 程序由互相协作的**对象**构成，每个对象封装数据（属性）和行为（方法） | 隐藏在对象内部 | 建模真实实体；大型、可扩展的系统 |
| 声明式 | 描述什么是真的（事实和规则），让系统去推理以满足目标 | 不逐步描述 | 逻辑/关系问题：家谱、基于规则的专家系统 |

> 现代语言往往支持多种范式（Java、VB.NET 和 Python 既是命令式又是面向对象）。答题时请固定在一种范式内，并明确写出所用的构造。

## 2. 低级语言

低级语言代码使用 CPU 自身的指令。**寻址方式**是 CPU 定位操作数时遵循的规则。这里是范式层面的回顾；具体指令集记号沿用 [[30 Computer Science/01 Topics/04 Processor Fundamentals/10 Lecture Notes|Topic 4 Processor Fundamentals]]。CAIE 操作数直接写成 `LDD 100`，`M[100]` 这类记号只用于解释内存效果。

| 寻址方式 | 操作数的定位方法 | 助记符示例 | 效果 |
|----------|------------------|------------|------|
| 立即数 | 操作数就是指令中写出的值本身 | `LDM #5` | ACC ← 5 |
| 直接 | 操作数存放在给出的地址处 | `LDD 100` | ACC ← M[100] |
| 间接 | 给出的地址里存放的是*另一个*地址，操作数在那个地址 | `LDI 100` | ACC ← M[M[100]] |
| 变址 | 操作数在（给出地址 + 变址寄存器）处 | `LDX 100` | ACC ← M[100 + IX] |
| 相对 | 地址是相对于当前 PC 的偏移量 | `JMP +3`（概念） | 跳到 PC + 偏移量 |

每种方式各一条示例指令：

```pseudocode
LDM #10         // 立即数：把字面量 10 装入 ACC
LDD 500         // 直接：   装入地址 500 处存放的值
LDI 500         // 间接：   地址 500 存放一个地址，从那里装入
LDX 500         // 变址：   从地址 500 + IX 处装入（数组元素）
JMP +3          // 相对：   从 PC 向前跳 3 条指令
```

变址寻址是数组的主力：存放数组基地址，再通过改变 IX 遍历各元素。相对寻址能生成位置无关代码——同样的字节无论装入何处都能正确运行。

## 3. 命令式/过程式编程

命令式编程把*如何*求解描述为一连串语句：读写变量、调用过程和函数。结构化编程的骨架来自 AS 11.3：顺序、选择（`IF`/`CASE`）和迭代（`FOR`/`WHILE`/`REPEAT`），并把可复用逻辑放进**过程**（作为语句调用）和**函数**（因返回一个值，可用在表达式中）。

一个简短示例——求数组中正数之和的函数：

```pseudocode
FUNCTION SumPositive(Values : ARRAY[1:10] OF INTEGER) RETURNS INTEGER
    DECLARE Total, i : INTEGER
    Total ← 0
    FOR i ← 1 TO 10
        IF Values[i] > 0 THEN
            Total ← Total + Values[i]
        ENDIF
    NEXT i
    RETURN Total
ENDFUNCTION

DECLARE Result : INTEGER
Result ← SumPositive(ExamMarks)   // 函数用在表达式内
OUTPUT "Total positive marks: ", Result
```

> 复习要点：次数固定用 `FOR`；可能一次都不执行用 `WHILE`；循环体必须先执行一次用 `REPEAT`。仅当调用方的变量需要改变时才用 `BYREF`。

## 4. 面向对象编程（OOP）

OOP 把问题建模为一组互相协作的**对象**。考官期望的术语如下：

| 术语 | 含义 |
|------|------|
| 类（class） | 模板，定义某一类对象共有的属性和方法 |
| 对象（object） | 由类创建出来的单一实体，即一个**实例** |
| 实例（instance） | 某个类的具体对象（各有自己的属性值） |
| 属性/性质（property/attribute） | 对象持有的一个命名数据 |
| 方法（method） | 属于类的过程或函数，即对象的行为 |
| 封装（encapsulation） | 把数据与处理它的代码捆绑在一起，并对外隐藏内部细节 |
| 取值方法（getter） | 返回某个私有属性值的方法 |
| 赋值方法（setter） | 给某个私有属性赋值的方法，通常带有效性检查 |
| 继承（inheritance） | 子类继承父类的属性和方法，并可扩展或覆盖 |
| 多态（polymorphism） | 不同对象对同一方法调用各自作出不同响应（常通过覆盖实现） |
| 包含/聚合（containment/aggregation） | 一个类由其他对象组装而成（"has-a"关系） |

**类的设计。** 先列出问题中的名词——每个候选都可能是一个类。每个类拥有它必须记住的属性和必须执行的方法。把属性标记为私有，通过取值/赋值方法对外暴露，这样外界就无法破坏数据。只有当一类确实*是一个*另一类时才用继承；当一个类*拥有*其他对象作为组成部分时用包含。

示例——`Vehicle` 类加一个 `Car` 子类，展示封装（私有属性）、取值方法与带有效性检查的赋值方法、继承，以及多态（覆盖 `describe`）：

```python
class Vehicle:
    def __init__(self, make, top_speed):
        self.__make = make            # 封装属性
        self.__top_speed = top_speed

    def get_make(self):               # 取值方法
        return self.__make

    def get_top_speed(self):          # 取值方法
        return self.__top_speed

    def set_top_speed(self, value):   # 带校验的赋值方法
        if value >= 0:
            self.__top_speed = value

    def describe(self):               # 方法，下面被覆盖
        return "Vehicle: " + self.__make


class Car(Vehicle):                   # 继承：Car is a Vehicle
    def __init__(self, make, top_speed, doors):
        super().__init__(make, top_speed)
        self.__doors = doors

    def describe(self):               # 多态：覆盖 Vehicle.describe
        return "Car: " + self.get_make() + " (" + str(self.__doors) + " doors)"


v = Vehicle("Honda", 180)            # 两个实例
c = Car("Tesla", 250, 4)
c.set_top_speed(260)                 # 用赋值方法修改私有值
print(v.describe())                  # Vehicle: Honda
print(c.describe())                  # Car: Tesla (4 doors)
```

一个持有多个 `Vehicle` 实例的车队对象就体现了**包含/聚合**——车队*拥有*车辆。

## 5. 声明式编程

声明式编程（逻辑式编程）不逐步说明*如何*计算。你用**事实**陈述什么是真的，用**规则**组合事实，再提出一个**目标**（查询），由系统通过匹配事实和规则去满足它。本主题通常采用 Prolog 风格记法。

- **事实（fact）**——声明某种关系成立，如 `parent(tom, bob).`
- **规则（rule）**——带条件的关系，写作 `head :- body.`；当 body 每一部分都为真时，head 才为真。
- **目标（goal）**——形如 `?- grandparent(tom, ann).` 的查询，系统回答 `yes`/`no`（并可绑定变量）。

示例——由一组事实构建家谱，用两条 parent 事实写出 grandparent 规则，再提出两个目标：

```prolog
% 事实：谁是誰的父母
parent(tom, bob).
parent(mary, bob).
parent(bob, ann).
parent(bob, sue).

% 规则：若 X 是 Y 的父母，且 Y 是 Z 的父母，则 X 是 Z 的祖父母
grandparent(X, Z) :- parent(X, Y), parent(Y, Z).

% 目标
?- grandparent(tom, ann).   % yes —— tom -> bob -> ann
?- grandparent(mary, sue).  % yes —— mary -> bob -> sue
?- grandparent(ann, tom).   % no
```

系统满足 `grandparent(tom, ann)` 的方式是找到一个 `Y`（bob），使得 `parent(tom, bob)` 和 `parent(bob, ann)` 都成立。新增规则不需要新事实——同一组事实可被复用。

## 6. 文件处理

文件把数据存放在后备存储器上，使程序结束后数据仍然保留。大纲中的三种文件**组织方式**因记录存放方式不同，适用的操作也不同。

| 组织方式 | 记录存放方式 | 访问模式 | 添加记录 | 查找某条记录 | 典型用途 |
|----------|--------------|----------|----------|--------------|----------|
| 串行文件 | 按到达顺序，无关键字 | 从头到尾读，不能跳过 | 追加到末尾 | 需搜遍整个文件 | 日志文件、传感器/事件数据 |
| 顺序文件 | 按关键字排序 | 按关键字顺序从头到尾读 | 插入到正确关键字位置 | 读到该关键字（或越过它） | 工资、对已排序数据的批处理 |
| 随机文件 | 固定长度记录存放在算出的地址 | 经地址直达任意记录 | 写入空闲槽位 | `SEEK` 后 `GETRECORD`，无需扫描 | 实时查询、索引 |

无论用哪种语言，伪代码操作都相同：以某种**模式**打开、读写记录、再关闭。一个文件一次只能以一种模式打开，当没有更多记录时 `EOF()` 返回 `TRUE`。

顺序文件——逐条读取并输出姓名：

```pseudocode
DECLARE MemberRecord : STRING

OPENFILE "Members.dat" FOR READ
WHILE NOT EOF("Members.dat")
    READFILE "Members.dat", MemberRecord
    OUTPUT MemberRecord
ENDWHILE
CLOSEFILE "Members.dat"
```

追加新记录（串行或顺序——都在末尾或按关键字位置添加）：

```pseudocode
OPENFILE "Log.dat" FOR APPEND
WRITEFILE "Log.dat", NewEntry
CLOSEFILE "Log.dat"
```

随机文件——按地址定位记录、读取、修改字段、再写回：

```pseudocode
DECLARE Rec : MemberRecord

OPENFILE "Data.dat" FOR RANDOM
SEEK "Data.dat", RecordIndex      // 把指针移到该记录地址
GETRECORD "Data.dat", Rec          // 读取定长记录
Rec.Status ← "Paid"
PUTRECORD "Data.dat", Rec          // 把更新后的记录写回
CLOSEFILE "Data.dat"
```

> 模式：`READ`、`WRITE`（创建新文件——已有数据丢失）、`APPEND`（追加到末尾）。随机文件用 `RANDOM`，配合 `SEEK`、`GETRECORD` 和 `PUTRECORD`。结束后一定要 `CLOSEFILE`；忘记关闭可能丢失缓冲区数据。

## 7. 异常与异常处理

**异常**是程序运行期间产生的错误状态，例如除以零、文件缺失、数组下标越界或输入非法。若不处理，程序会崩溃。**异常处理**在程序能够合理应对的位置（显示提示、使用默认值、重试）捕获该状态，使执行得以继续或干净地结束，而不是中途夭折。

当某种故障**可能发生但并非正常**、且你确有恢复路径时，才适合使用异常处理：读取用户指定名称的文件、解析输入、除以可能为零的值。不要把每条语句都包起来——捕获过宽会掩盖真实缺陷。先捕获最具体的错误，再用一个通用捕获兜底。

Java 示例——用用户输入的值去除 100，针对除以零给出具体捕获：

```java
import java.util.Scanner;

class Main {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("Enter a divisor: ");
        try {
            int d = in.nextInt();
            int result = 100 / d;            // 可能抛出 ArithmeticException
            System.out.println("100 / " + d + " = " + result);
        } catch (ArithmeticException e) {    // 除以零
            System.out.println("Cannot divide by zero.");
        } catch (Exception e) {              // 其他任何失败，例如输入非法
            System.out.println("Invalid input.");
        }
    }
}
```

CAIE Pseudocode Guide 没有定义异常处理伪代码。Paper 4 要求用所选语言写真实程序代码。Visual Basic .NET 和 Python 中的同一模式如下：

```vbnet
Module MainModule
    Sub Main()
        Console.Write("Enter a divisor: ")
        Try
            Dim d As Integer = Integer.Parse(Console.ReadLine())
            Dim result As Integer = 100 \ d
            Console.WriteLine("100 / " & d & " = " & result)
        Catch ex As DivideByZeroException   ' 除以零
            Console.WriteLine("Cannot divide by zero.")
        Catch ex As Exception               ' 其他失败，例如输入非法
            Console.WriteLine("Invalid input.")
        End Try
    End Sub
End Module
```

```python
try:
    d = int(input("Enter a divisor: "))
    result = 100 / d
    print("100 /", d, "=", result)
except ZeroDivisionError:           # 除以零
    print("Cannot divide by zero.")
except Exception:                   # 其他失败，例如输入非法
    print("Invalid input.")
```

三种 Paper 4 语言的模式相同：把可能失败的语句放入该语言的保护块，先捕获 `ArithmeticException` / `DivideByZeroException` / `ZeroDivisionError`，再用更宽泛的 `Exception` 兜底，并让每个处理分支做有意义的恢复或提示。

## 做题顺序

1. 先判断题目要求的范式，并固定在其中；明确写出所用的构造。
2. 低级语言题：写助记符前先确定每条指令需要的寻址方式。
3. OOP：列出类（名词）、它们的属性和方法；标记私有数据并规划取值/赋值方法；仅对"is-a"使用继承。
4. 声明式：先写全部事实，再写组合它们的规则，最后精确表述目标。
5. 文件：先确定模式再打开；顺序文件用 `EOF()` 循环，随机文件用 `SEEK`；每个文件都要关闭。
6. 异常：列出所有可能失败之处，先捕获最具体的，并提供真正可执行的恢复动作。

## 常见错误

- 在一个答案里混用多种范式（例如在 OOP 设计里加全局变量）。
- 把直接寻址（`LDD`，一个地址）和间接寻址（`LDI`，地址里再存地址）搞混。
- 把属性设为公有并跳过取值/赋值方法，从而丢掉封装分。
- 该用包含（"has-a"）时却用了继承。
- 忘记 `CLOSEFILE`，或在需要 `APPEND` 时用 `WRITE` 打开文件。
- 捕获一个空泛的 `Exception` 掩盖真实故障，或处理根本不可能发生的异常。

## 快速自查

- 说出四种范式以及各自最适合的一种场景。
- 为五种寻址方式各写一条取数指令并说明其效果。
- 设计一个 `BankAccount` 类，含私有余额、一个取值方法和一个带有效性检查的赋值方法。
- 用 `parent/2` 事实写一条 `sibling(X, Y)` 的声明式规则。
- 写出向顺序文件追加记录、以及更新随机文件记录的伪代码。
- 用你的 Paper 4 语言写一段处理“文件缺失”错误的异常处理代码，并说明为什么要先捕获具体异常。

## 关联内容

- [[30 Computer Science/01 Topics/11 Programming/00 Overview|Programming]] —— 本主题扩展的 AS 基础。
- [[30 Computer Science/01 Topics/13 Data Representation/00 Overview|Data Representation]] —— 此处使用的文件组织方式和记录类型。
- [[30 Computer Science/04 Reference/Pseudocode and Programming Reference|Pseudocode and Programming Reference]] —— 文件处理、异常与 Paper 4 语言对照。
