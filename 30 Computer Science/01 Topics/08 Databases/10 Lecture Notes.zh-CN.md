---
title: Databases 中文讲义
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/08 Databases/00 Overview|Databases]]"
status: active
tags:
  - computerscience/data
  - lecture-notes
  - zh-CN
---

# Databases 中文讲义

数据库把相关数据集中存放，以便查询、保持一致并加以保护。本节涵盖层层递进的三个部分：关系模型的*概念*（为什么要放弃文件式处理，以及实体、键、关系等精确术语）、运行它的*软件*（DBMS 及其工具），以及定义和操作数据的*语言*（SQL，分为 DDL 和 DML）。三者在 Paper 1 中都会考查，必须作为一个整体来学，而不是三组互不相干的知识点。

## 来源范围

本讲义对应 CAIE 9618 AS 第 8 节 Databases：

- 8.1 Database Concepts：文件式处理的局限，以及关系数据库如何解决它们；关系术语（实体、表、记录、字段、元组、属性、主键、候选键、辅键、外键，关系 1:1/1:M/M:N，参照完整性，索引）；实体-关系图（E-R）；规范化至 1NF、2NF、3NF。
- 8.2 DBMS：功能（数据字典、数据建模、逻辑模式、数据完整性、通过备份和访问权限实现的数据安全）与工具（开发者接口、查询处理器）。
- 8.3 DDL 和 DML：DDL 创建和修改结构，DML 查询和维护数据，SQL 是工业标准；DDL（CREATE DATABASE、CREATE TABLE 及 CHARACTER/VARCHAR(n)/BOOLEAN/INTEGER/REAL/DATE/TIME 类型、ALTER TABLE、PRIMARY KEY、FOREIGN KEY ... REFERENCES）；DML（SELECT ... FROM、WHERE、ORDER BY、GROUP BY、INNER JOIN、SUM、COUNT、AVG、INSERT INTO、DELETE FROM、UPDATE）至多涉及两张表。
- 在 Paper 1 中考查。

## 1. 文件式处理的局限与关系模型的解决之道

**文件式处理（file-based approach）** 让每个应用程序各自维护*自己的*一批文件，并各自编写读写这些文件的代码。看似简单，却会带来一系列众所周知的问题，关系数据库正是为解决这些问题而诞生的。要把*问题*和*对应的解决功能*一起记。

| 文件式处理的局限 | 关系数据库如何解决 |
| --- | --- |
| **数据冗余**——同一份数据（某客户的地址）被录入到多个文件里，既浪费空间，又在只更新其中一份时造成不一致。 | 数据在表中只存*一份*，用键来*引用*；这唯一的一份就是权威来源。 |
| **数据不一致**——各副本可能对不上，没人知道哪个是对的。 | 只有一份就意味着只有一个值；一处更新，处处生效。 |
| **数据依赖**——文件的物理格式被硬编码进程序，存储方式一变，程序就坏了。 | DBMS 用*逻辑模式*把物理存储藏起来；程序面对的是表，而不是文件。 |
| **数据完整性差**——没人能阻止一张订单引用一个根本不存在的客户。 | DBMS 强制的**参照完整性**会拦住那些指向不存在主键的外键。 |
| **缺乏数据共享 / 并发**——一个程序锁住文件，另一个程序就没法同时工作。 | DBMS 统一管理并发访问，让多个用户安全地共享数据。 |
| **缺乏集中安全**——每个文件由各自的应用程序保护（或根本不保护）。 | DBMS 在所有数据之上统一施加*访问权限*和*备份*。 |

简而言之：关系数据库减少*冗余*、提升*完整性*、提供*数据独立性*（程序看到的是表而非物理文件）、允许*共享*，并提供*集中的安全和备份*。如果题目问"指出文件式处理的一个局限"，挑一行，把局限*和*关系模型如何补救都说出来。

## 2. 关系术语

考试用的是一套精确的术语。有几个词近乎同义（实体 ≈ 表；元组 ≈ 记录；属性 ≈ 字段），要把概念层面的词和表层面的词成对来记。

| 术语 | 含义 |
| --- | --- |
| **实体（entity）** | 数据库所要建模的现实"事物"——客户、订单、零件。每个实体成为一张*表*。 |
| **表（table，关系 relation）** | 一个由行和列组成的二维结构，存放一个实体的数据。 |
| **记录（record，元组 tuple）** | 一*行*——关于某个实体的一个实例的全部数据，例如一位客户。 |
| **字段（field，属性 attribute）** | 一*列*——每条记录都存储的一个属性，例如 `CustomerName`。 |
| **主键（primary key，PK）** | 唯一标识一条记录、且永不为空的一个（或一组）属性。每张表有且只有一个主键。 |
| **候选键（candidate key）** | *任何*能充当主键的属性——即唯一且非空的字段。从中选一个做主键，其余的就是备用键。 |
| **辅键（secondary key）** | 经常用于*查找或排序*的属性，在其上建索引以加速（它不必唯一）。 |
| **外键（foreign key，FK）** | 某张表中的一个属性，其值*引用*另一张表的主键，从而在两表之间建立联系。 |
| **关系（relationship）** | 两个实体之间的关联。有三种：**1:1**（一对一）、**1:M**（一对多，最常见）、**M:N**（多对多，必须通过*链接表*化解）。 |
| **参照完整性（referential integrity）** | 由 DBMS 强制的一条规则：外键要么匹配被引用表中已存在的主键，要么为空——绝不指向不存在的记录。 |
| **索引（indexing）** | 在某个字段上额外建立的数据结构（就像书的索引），使记录能被*快速定位*而无需扫描整张表；以额外的存储和更慢的写入换取查找和排序的速度。 |

有两对容易混淆。**主键与候选键**：候选键是*任何*唯一且非空的字段；主键是*你选定的那一个*。**辅键与外键**：辅键用于在某张表*内部快速查找*；外键用于*链接到另一张表*。

## 3. 实体-关系图（E-R）

**实体-关系图（E-R diagram）** 是实体及其关系的示意图，在动手建表或写 SQL *之前*先画。CAIE 的记法很简单，必须照原样复现。

| 元素 | 记法 | 含义 |
| --- | --- | --- |
| **实体** | 一个**矩形**，里面写实体名（例如 `CUSTOMER`） | 一个"事物"——会变成一张表 |
| **关系** | 连接两个实体的一条**线**，线上写一个动词（例如 `places`） | 实体之间的关联 |
| **基数（cardinality）** | 线两端的符号或数字：`1`、`M` 或 `N`；或用鸦爪记号 | 每一方各有多少参与（1:1、1:M、M:N） |

读图时，沿着线走，读*两端的*基数，并点名那一端的实体。`CUSTOMER ---places--- ORDER`，客户端是 `1`，订单端是 `M`，读作：**一个**客户下达**多个**订单；每个订单恰好属于一个客户——一对多关系。

画图的步骤：

1. 找出**实体**（那些名词：客户、订单、零件）——每个画一个矩形。
2. 在它们之间画**线**，每条线上写一个**动词**。
3. 在两端加**基数**（`1` / `M` / `N`）。
4. 遇到**多对多**（M:N）关系，绝不要放着不管：在中间插入一个**链接实体**（也叫交叉表、桥接表），把它拆成两个一对多关系。例如 `STUDENT` M:N `SUBJECT` 就变成 `STUDENT` 1:M `ENROLMENT` M:1 `SUBJECT`。

基数和链接表的规则是两大常考点；图形记法始终是：矩形 = 实体，线 = 关系。

## 4. 规范化

**规范化（normalisation）** 是逐步重组一张表的过程，目的是消除*冗余*（重复数据）和*更新异常*，得到高效且不会不一致的设计。共有三个阶段，每阶段修掉一类特定问题。要记的定义是：

- **第一范式（1NF）**——没有**重复组**；每个字段都是*原子的*（只含单个值）；每条记录都有主键。重复的列被拆成多行或抽到新表。
- **第二范式（2NF）**——已是 1NF，*且*每个非键属性依赖于**整个**主键，而不是主键的一部分。（只有当主键是**复合的**——由两个或更多字段组成——时才需要考虑。单字段主键的表，只要满足 1NF，就自动满足 2NF。）
- **第三范式（3NF）**——已是 2NF，*且*每个非键属性*只*依赖于主键：非键字段之间不存在依赖（不存在*传递依赖*，例如 `PostCode → City`）。

简记口诀：每个非键字段必须依赖**键**（1NF）、**整个键**（2NF）、**除了键啥都不依赖**（3NF）。遇到"这张表是不是 3NF"的题，依次检查：有没有重复组？有没有只依赖部分主键的？有没有非键依赖非键的？第一个"有"就告诉你它处在哪一范式。

### 示例：一张发票，从非规范化到 3NF

从一个**非规范化**的发票视图出发，每行都重复客户和订单信息，并把所有零件挤在一行里：

| InvoiceNo | CustomerID | CustomerName | OrderDate | PartNo | PartDescription | Qty | PartPrice |
| --- | --- | --- | --- | --- | --- | --- | --- |
| INV-01 | C100 | Acme | 2026-07-01 | P5, P7 | Bolt, Nut | 10, 4 | 0.20, 0.15 |
| INV-02 | C101 | Beta | 2026-07-01 | P5 | Bolt | 25 | 0.20 |

问题：`PartNo`、`PartDescription`、`Qty` 和 `PartPrice` 字段各自装着*多个值*（一个重复组），这一行不是原子的。

**第一步——化为 1NF。** 去掉重复组：给每个零件单独一行，发票数据复制下来。加一个主键。

1NF `INVOICE`（主键 = `InvoiceNo, PartNo`——复合键，因为单凭任何一个都不唯一）：

| InvoiceNo | CustomerID | CustomerName | OrderDate | PartNo | PartDescription | Qty | PartPrice |
| --- | --- | --- | --- | --- | --- | --- | --- |
| INV-01 | C100 | Acme | 2026-07-01 | P5 | Bolt | 10 | 0.20 |
| INV-01 | C100 | Acme | 2026-07-01 | P7 | Nut | 4 | 0.15 |
| INV-02 | C101 | Beta | 2026-07-01 | P5 | Bolt | 25 | 0.20 |

没有了重复组，每个字段都是原子的。但出现了严重的*重复*（Acme 和日期被重复），还有*部分键依赖*：`CustomerID`、`CustomerName` 和 `OrderDate` 只依赖 `InvoiceNo`，而 `PartDescription` 和 `PartPrice` 只依赖 `PartNo`。

**第二步——化为 2NF。** 去掉部分键依赖：每个非键字段必须依赖*整个*键。拆成三张表。

`INVOICE`（主键 = `InvoiceNo`）：

| InvoiceNo | CustomerID | OrderDate |
| --- | --- | --- |
| INV-01 | C100 | 2026-07-01 |
| INV-02 | C101 | 2026-07-01 |

`PART`（主键 = `PartNo`）：

| PartNo | PartDescription | PartPrice |
| --- | --- | --- |
| P5 | Bolt | 0.20 |
| P7 | Nut | 0.15 |

`INVOICE_PART`（主键 = `InvoiceNo, PartNo`——即原复合键演变来的链接表）：

| InvoiceNo | PartNo | Qty |
| --- | --- | --- |
| INV-01 | P5 | 10 |
| INV-01 | P7 | 4 |
| INV-02 | P5 | 25 |

现在每个非键字段都依赖于其所在表的整个键。此时 `CustomerName` 还留在 `INVOICE` 里——它依赖整个键（一个单字段键），所以 2NF 已经满足，但仍藏着一个依赖。

**第三步——化为 3NF。** 去掉非键到非键（传递）的依赖。在 `INVOICE` 里，`CustomerName` 依赖的是 `CustomerID`，而 `CustomerID` *不是*主键——这是个传递依赖。把它拆出来。

`CUSTOMER`（主键 = `CustomerID`）：

| CustomerID | CustomerName |
| --- | --- |
| C100 | Acme |
| C101 | Beta |

`INVOICE`（主键 = `InvoiceNo`；`CustomerID` 现在是**外键**）：

| InvoiceNo | CustomerID | OrderDate |
| --- | --- | --- |
| INV-01 | C100 | 2026-07-01 |
| INV-02 | C101 | 2026-07-01 |

最终的规范化设计有四张表：

- `CUSTOMER`（**CustomerID**，CustomerName）
- `INVOICE`（**InvoiceNo**，CustomerID*（外键）*，OrderDate）
- `PART`（**PartNo**，PartDescription，PartPrice）
- `INVOICE_PART`（**InvoiceNo** *（外键）*，**PartNo** *（外键）*，Qty）

现在每个非键字段都依赖键、整个键、除了键啥都不依赖；除了用作外键链接的键以外，没有数据重复。注意那个"一张发票包含多个零件，一个零件出现在多张发票上"的多对多关系，是如何被链接表 `INVOICE_PART` 化解的——这和 E-R 图里的链接实体是同一个道理。

## 5. DBMS 的功能与工具

**数据库管理系统（DBMS）** 是介于用户 / 应用程序与存储数据之间的那层软件，提供文件式处理所欠缺的各项功能和工具。

**功能（features）**——DBMS *提供什么*：

| 功能 | 作用 |
| --- | --- |
| **数据字典（data dictionary）** | 存放*元数据*——每张表、每个字段、每个类型、每个键和每个关系的描述。DBMS 借助它来了解数据库的结构。 |
| **数据建模（data modelling）** | 支持在实现之前先设计数据结构（常通过 E-R 图）。 |
| **逻辑模式（logical schema）** | 数据库的*整体逻辑结构*（表、字段、键、关系），与物理存储方式无关。正是它带来了数据独立性。 |
| **数据完整性（data integrity）** | 强制那些保证数据正确的规则——*实体完整性*（主键唯一且非空）和*参照完整性*（外键必须匹配已存在的主键或为空）。也可以定义验证规则。 |
| **数据安全（data security）** | 对数据的集中保护：**备份**（定期复制，使数据在丢失后能恢复）和**访问权限**（每个用户 / 角色只授予其所需的读 / 写 / 删除权限）。 |

**工具（tools）**——DBMS *向用户 / 开发者暴露什么*：

| 工具 | 作用 |
| --- | --- |
| **开发者接口（developer interface）** | 开发者用来定义和维护数据库的环境——编写 DDL、设计模式、管理结构。 |
| **查询处理器（query processor）** | 接收一个查询（例如 SQL `SELECT`），解析并优化它，规划如何针对物理存储执行它，再返回结果的组件。它让人能在不了解物理布局的情况下使用逻辑模式。 |

清晰的划分是：*功能*是 DBMS 为保证数据正确、独立和安全而提供的能力；*工具*是让人和程序得以使用这些数据的接口。

## 6. SQL——DDL 与 DML

**SQL** 是关系数据库的工业标准语言。它清楚地分成两半：

- **数据定义语言（DDL）**——*创建或修改数据库结构*的语句（数据库、表、字段、类型、键）。它们改的是*模式*，不是数据。
- **数据操纵语言（DML）**——*查询或维护数据本身*的语句（检索、插入、更新、删除行）。它们改的是*内容*，不是结构。

一条语句如果是关于数据库形状的，就是 DDL；如果是关于表里那些行的，就是 DML。

### DDL——数据定义

DDL 语句和考纲点名的 SQL 数据类型：

| 语句 / 类型 | 用途 |
| --- | --- |
| `CREATE DATABASE` | 创建一个新数据库。 |
| `CREATE TABLE` | 创建一张新表及其列。 |
| `ALTER TABLE` | 修改已有表的结构（添加、删除或更改列；添加键）。 |
| `PRIMARY KEY (field)` | 声明唯一标识一行的列（或多列）。 |
| `FOREIGN KEY (field) REFERENCES Table (Field)` | 声明一个外键，链接到另一张表的主键。 |
| `CHARACTER` | 定长字符串。 |
| `VARCHAR(n)` | 变长字符串，最多 `n` 个字符。 |
| `BOOLEAN` | 真值（`TRUE` / `FALSE`）。 |
| `INTEGER` | 整数。 |
| `REAL` | 带小数部分的数（浮点）。 |
| `DATE` | 日历日期。 |
| `TIME` | 一天中的时间。 |

示例——按规范化设计创建 `CUSTOMER` 和 `INVOICE` 这两张相关表，带主键和外键：

```sql
CREATE DATABASE SalesDB;

CREATE TABLE Customer (
    CustomerID     CHARACTER(4),
    CustomerName   VARCHAR(40),
    PRIMARY KEY (CustomerID)
);

CREATE TABLE Invoice (
    InvoiceNo      CHARACTER(6),
    CustomerID     CHARACTER(4),
    OrderDate      DATE,
    PRIMARY KEY (InvoiceNo),
    FOREIGN KEY (CustomerID) REFERENCES Customer (CustomerID)
);
```

`Invoice.CustomerID` 上的外键引用 `Customer.CustomerID`；DBMS 现在会强制**参照完整性**，拒绝任何 `CustomerID` 在 `Customer` 表里不存在的发票。建表之后要改动，用 `ALTER TABLE`，例如加一列：`ALTER TABLE Customer ADD CustomerEmail VARCHAR(60);`——这属于 DDL，因为它改的是结构，不是数据。

### DML——数据操纵

考纲点名的 DML 语句和子句 / 函数（查询至多涉及*两张表*）：

| 子句 / 函数 | 用途 |
| --- | --- |
| `SELECT ... FROM` | 选择要输出的列以及读取的表——即*投影*。 |
| `WHERE` | 筛选出满足条件的行——即*选择*。 |
| `ORDER BY` | 对结果行排序（升序或降序）。 |
| `GROUP BY` | 把取值相同的行归为一组，以便对每组计算*聚合*值。 |
| `INNER JOIN` | 在连接条件匹配时合并两表的行（只保留匹配的行）。 |
| `SUM` | 对一个数值列求和。 |
| `COUNT` | 计数行数（或非空值个数）。 |
| `AVG` | 对一个数值列求平均。 |
| `INSERT INTO` | 添加新行。 |
| `DELETE FROM` | 删除满足条件的行。 |
| `UPDATE` | 更改已有行中的值。 |

示例——列出每位客户在 2026 年 7 月 1 日以来的发票中，订购数量的总和与平均值，连接 `Invoice` 和 `InvoicePart`。这里用到了 `INNER JOIN`、`WHERE`、`GROUP BY` 和两个聚合函数：

```sql
SELECT Invoice.CustomerID,
       SUM(InvoicePart.Qty) AS TotalQty,
       AVG(InvoicePart.Qty) AS AvgQty
FROM   Invoice
INNER JOIN InvoicePart ON Invoice.InvoiceNo = InvoicePart.InvoiceNo
WHERE  Invoice.OrderDate >= '2026-07-01'
GROUP BY Invoice.CustomerID
ORDER BY TotalQty DESC;
```

按这个顺序读：哪些表（`FROM` + `INNER JOIN`），哪些行（`WHERE`），如何分组（`GROUP BY`），算什么（`SUM`、`AVG`），最后怎么排序（`ORDER BY`）。数据维护的例子：用 `INSERT INTO Part (PartNo, PartDescription, PartPrice) VALUES ('P9', 'Washer', 0.05);` 添加新零件，用 `DELETE FROM Invoice WHERE CustomerID = 'C101';` 删除某客户的发票，用 `UPDATE Part SET PartPrice = 0.25 WHERE PartNo = 'P5';` 调价。这三条都是 DML：改的是*内容*，不是结构。

## 做题顺序

1. 遇到"文件式处理的局限"题，点名一个局限，*并*说明关系模型如何补救——各一句具体的话。
2. 遇到术语题，把概念层的词和表层的词配对（实体 / 表、元组 / 记录、属性 / 字段），并说明该键是为了唯一（主键 / 候选键）、为了链接（外键）还是为了快速查找（辅键）。
3. 遇到 E-R 题，为每个实体画矩形，线上写动词，两端标基数；如果看到多对多，就插入一个链接实体。
4. 遇到规范化题，一步一步走：1NF 去重复组并定主键；2NF 去部分键依赖（注意有没有复合键）；3NF 去非键对非键的依赖。写出结果表，给每个键画下划线。
5. 遇到 DDL 题，先定表、列和类型，再定主键，最后定外键及其 `REFERENCES`。
6. 遇到 DML 查询题，按 表 → 连接 → 筛选 → 分组 → 聚合 → 排序 的顺序读，并按此顺序写。

## 常见错误

- 只写了局限或只写了解决办法。文件式处理的题要既给问题、又给关系模型的补救功能。
- 把**候选键**（任何唯一非空字段）和**主键**（你选定的那一个）搞混。
- 把**辅键**当成外键。辅键加速的是某张表*内部的查找*；外键是用来*链接到另一张表*的。
- 画了多对多关系却不化解。M:N 必须用链接表拆开。
- 在还有非键字段依赖另一个非键字段（例如 `PostCode → City`）时就停在了 2NF。
- 忘记 2NF 只对**复合键**有意义；单字段主键的表只要满足 1NF，就已是 2NF。
- 加外键时忘了参照完整性——它必须引用一个已存在的主键。
- 把**DDL**（结构：`CREATE`、`ALTER`）和**DML**（数据：`SELECT`、`INSERT`、`UPDATE`、`DELETE`）混在一起。
- 把连接条件写进 `WHERE` 而不是 `ON`，或者 `INNER JOIN` 漏了 `ON`。
- 需要分组汇总时用了聚合函数（`SUM`、`COUNT`、`AVG`）却不加 `GROUP BY`。

## 快速自查

如果下面这些问题不看笔记也能答上来，就可以进入下一节。

1. 指出文件式处理的一个局限，以及对应的关系模型补救功能。
2. 用一句话分别定义实体、表、记录、字段。
3. 各用一行区分主键、候选键、辅键、外键。
4. 解释参照完整性，并举例说明它会拦下哪一种插入。
5. 说出三种关系基数，并指出哪一种需要链接表。
6. 画出 `STUDENT` M:N `SUBJECT` 的 E-R 图，把它化解成两个一对多关系。
7. 用"键、整个键、除了键啥都不依赖"的形式口述 1NF、2NF、3NF 的规则。
8. 拿上面的发票数据，凭记忆重新推出四张 3NF 表和全部键。
9. 解释为什么单字段主键的表不可能不满足 2NF。
10. 写出两张相关表的 `CREATE TABLE` 语句，带主键和外键，至少用到四种不同的数据类型。
11. 写一条用到 `INNER JOIN`、`WHERE`、`GROUP BY` 和 `SUM` 的 SQL 查询。
12. 用一句话把 DBMS 的*功能*和*工具*分开，各举两个。

## 关联内容

- [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/00 Overview|Security, Privacy and Data Integrity]] 提供了这里作为 DBMS 数据完整性与数据安全功能出现的验证、访问权限和备份等概念。
- [[30 Computer Science/01 Topics/10 Data Types and Structures/00 Overview|Data Types and Structures]] 与本节共享"结构化记录与字段类型"的思想，后者在此复现为 SQL 的数据类型和表的列。
