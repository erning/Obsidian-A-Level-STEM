---
title: Databases Worked Examples
subject: Computer Science
syllabus: 9618
parent: "[Databases](00%20Overview.md)"
status: active
tags:
  - computerscience/data
  - worked-examples
---

# Databases Worked Examples

These examples model how to reason through relational design, normalisation, and SQL questions in the style of CAIE 9618. The aim is to show the working that earns marks: identify the keys, justify each normalisation step with a dependency, and read SQL by separating target table, join, filter, and projection.

## Source Route

- Syllabus: CAIE Computer Science 9618, AS Section 8 - Databases.
- Assessed in Paper 1.
- Topics: file-based limitations and the relational model; relational terminology and keys; E-R diagrams; normalisation to 1NF, 2NF, 3NF; DBMS features; DDL (`CREATE DATABASE`, `CREATE TABLE`, `ALTER TABLE`, `PRIMARY KEY`, `FOREIGN KEY ... REFERENCES`); DML (`SELECT`, `WHERE`, `ORDER BY`, `GROUP BY`, `INNER JOIN`, `SUM`, `COUNT`, `AVG`, `INSERT`, `DELETE`, `UPDATE`).

## Example 1: File-based Limitation and the Relational Fix

**Prompt.** A school stores pupil data in one flat file per department, and each department also keeps its own copy of pupil contact details. State two problems this causes and explain how a relational database addresses each.

**Solution.**

- Problem 1: **data duplication**. Pupil contact details are repeated in every department file, so storage is wasted and updates must be repeated.
  - Relational fix: store pupil details once in a `Pupil` table. Departments reference a pupil by its primary key, so the contact data exists in only one place.
- Problem 2: **data inconsistency** (a consequence of duplication). If the address is updated in the Maths file but not the Science file, the two records disagree.
  - Relational fix: because the data lives in one table, an update is applied once and every department immediately sees the same value. This is a single source of truth.
- A further problem is **lack of shared access with controlled rights**, which a DBMS solves through a single managed store with per-user access rights.

**Check.** The relational answer is "store each fact once, link with keys". If your "fix" still allows the same data in two places, it is not a relational fix.

## Example 2: Identifying Keys in a Sample Table

**Prompt.** A `Pupil` table has fields `PupilID`, `Name`, `Form`, `Email`. State which fields could be a primary key, which are candidate keys, and a sensible secondary key.

**Solution.**

- `PupilID` is the natural **primary key**: it uniquely identifies a row and is short and stable. Each value occurs once.
- `Email` is a **candidate key**: it is also unique for every pupil, so it could in principle be the primary key. The designer chooses one candidate as the primary key.
- `Name` cannot be a key: two pupils can share a name, so it does not guarantee uniqueness.
- A sensible **secondary key** is `Name` or `Form`. A secondary key is not unique; it is used to speed up searches such as "list all pupils in Form 5B". It supports `ORDER BY` and `WHERE` lookups on non-unique values.

**Check.** A primary key must be unique and not null. A candidate key is any field that could serve that role. A secondary key is for searching, not for identifying.

## Example 3: E-R Diagram for a Small Scenario

**Prompt.** A college runs courses. Each course has many students enrolled on it, and each student can be enrolled on many courses. Each course is taught by exactly one tutor. Describe an E-R diagram for this, stating the entities, relationships, and their cardinalities.

**Solution.**

- Entities (rectangles): `Student`, `Course`, `Tutor`.
- Relationships (diamonds) and cardinalities:
  - `Student` is enrolled on `Course`: this is **many-to-many (M:N)**, because one student takes many courses and one course has many students. In a relational design an M:N relationship is implemented through a **link table** (for example `Enrolment` with the primary keys of `Student` and `Course` as foreign keys).
  - `Tutor` teaches `Course`: this is **one-to-many (1:M)**, because one tutor teaches many courses but a course is taught by exactly one tutor. The foreign key goes on the `Course` side.
- The diagram therefore reads: `Student` -M:N- `Course` -M:1- `Tutor`.

**Check.** For each pair, ask both questions: "how many X per Y?" and "how many Y per X?". If both answers are "many", it is M:N and needs a link table.

## Example 4: Normalising an Unnormalised Table to 3NF

**Prompt.** The following single table records orders. Normalise it to 3NF, showing each step and stating the keys.

Unnormalised `Order`:

| OrderNo | CustID | CustName | ItemCode | ItemDesc | Qty | UnitPrice |
|---------|--------|----------|----------|----------|-----|-----------|
| 101     | C7     | Aziz     | P1       | Pen      | 4   | 1.50      |
| 101     | C7     | Aziz     | P2       | Pad      | 2   | 2.00      |
| 102     | C9     | Bo       | P1       | Pen      | 1   | 1.50      |

**Solution.**

Step 1 - to **1NF**. The table already has atomic values and a single value in each cell, but the key is the combination `OrderNo, ItemCode`, since one order holds many items. There is a repeating group of items per order.

- 1NF `Order`: primary key `(OrderNo, ItemCode)`.
- Non-key attributes: `CustID`, `CustName`, `ItemDesc`, `Qty`, `UnitPrice`.

Step 2 - to **2NF**. Remove **partial dependencies**: attributes that depend on only part of the composite key.

- `ItemDesc` and `UnitPrice` depend only on `ItemCode`, not on `OrderNo`, so they move out.
- `CustID` and `CustName` depend only on `OrderNo`, not on `ItemCode`, so they move out.
- Only `Qty` depends on the whole key `(OrderNo, ItemCode)`.

Result:

- `Order(OrderNo, CustID)` - PK `OrderNo`.
- `OrderItem(OrderNo, ItemCode, Qty)` - PK `(OrderNo, ItemCode)`, FK `OrderNo` references `Order`, FK `ItemCode` references `Item`.
- `Item(ItemCode, ItemDesc, UnitPrice)` - PK `ItemCode`.

Step 3 - to **3NF**. Remove **transitive dependencies**: non-key attributes depending on another non-key attribute.

- In `Order`, `CustName` depends on `CustID`, not directly on `OrderNo`. So `CustID, CustName` move out into a `Customer` table.

Final 3NF design:

- `Order(OrderNo, CustID)` - PK `OrderNo`, FK `CustID` references `Customer`.
- `Customer(CustID, CustName)` - PK `CustID`.
- `OrderItem(OrderNo, ItemCode, Qty)` - PK `(OrderNo, ItemCode)`, FKs to `Order` and `Item`.
- `Item(ItemCode, ItemDesc, UnitPrice)` - PK `ItemCode`.

**Check.** At each stage ask: does every non-key attribute depend on the whole key (2NF) and on nothing but the key (3NF)? `Qty` survives both tests in `OrderItem`, so the design is in 3NF.

## Example 5: Spotting Why a Table is Not in 3NF

**Prompt.** A `Lesson` table has fields `LessonID` (primary key), `Room`, `Building`, `TeacherID`, `TeacherName`. The building is determined by the room, and the teacher name is determined by the teacher ID. Explain why this table is not in 3NF and state the corrected design.

**Solution.**

- The table is not in 3NF because of two **transitive dependencies**:
  - `Building` depends on `Room`, which is a non-key attribute. `Room -> Building` is the dependency, and `Room` is not a candidate key.
  - `TeacherName` depends on `TeacherID`, again a non-key attribute.
- A 3NF table must have every non-key attribute depending only on the primary key. Here `Building` and `TeacherName` depend on other non-key attributes.
- Corrected design (split out the transitively dependent groups):
  - `Lesson(LessonID, Room, TeacherID)` - PK `LessonID`.
  - `Room(Room, Building)` - PK `Room`.
  - `Teacher(TeacherID, TeacherName)` - PK `TeacherID`.
- `Lesson` now has foreign keys `Room` referencing `Room` and `TeacherID` referencing `Teacher`.

**Check.** Look for chains `Key -> X -> Y`. The middle attribute `X` (here `Room`, `TeacherID`) is the sign of a transitive dependency; move it to its own table.

## Example 6: DDL for Two Related Tables

**Prompt.** Write SQL DDL to create a `Department` table and an `Employee` table where each employee belongs to exactly one department. Department has `DeptID` (integer, primary key) and `DeptName` (variable character up to 40). Employee has `EmpID` (integer, primary key), `EmpName` (variable character up to 50), `Salary` (real), `HireDate` (date), and the department it belongs to.

**Solution.**

```sql
CREATE TABLE Department (
    DeptID    INTEGER,
    DeptName  VARCHAR(40),
    PRIMARY KEY (DeptID)
);

CREATE TABLE Employee (
    EmpID     INTEGER,
    EmpName   VARCHAR(50),
    Salary    REAL,
    HireDate  DATE,
    DeptID    INTEGER,
    PRIMARY KEY (EmpID),
    FOREIGN KEY (DeptID) REFERENCES Department(DeptID)
);
```

- `DeptID` in `Employee` is a **foreign key** that references the primary key of `Department`. This enforces **referential integrity**: you cannot insert an employee with a `DeptID` that does not exist, and you cannot delete a department that still has employees (unless cascade rules say otherwise).
- The "one" side (`Department`) is created before the "many" side (`Employee`) so the foreign key has a target to reference.

**Check.** Identify the "one" side first, create it first, and put the foreign key on the "many" side. Each `FOREIGN KEY ... REFERENCES` must point at an existing primary key.

## Example 7: DML Query with INNER JOIN and Aggregates

**Prompt.** Given `Employee(EmpID, EmpName, Salary, HireDate, DeptID)` and `Department(DeptID, DeptName)`, write SQL to show, for each department, the department name, the number of employees hired on or after 1 January 2020, the total salary of those employees, and their average salary. List the results from highest average salary to lowest.

**Solution.**

```sql
SELECT Department.DeptName,
       COUNT(Employee.EmpID),
       SUM(Employee.Salary),
       AVG(Employee.Salary)
FROM Department
INNER JOIN Employee ON Department.DeptID = Employee.DeptID
WHERE Employee.HireDate >= '2020-01-01'
GROUP BY Department.DeptName
ORDER BY AVG(Employee.Salary) DESC;
```

- `INNER JOIN` matches each employee to their department on the shared `DeptID`.
- `WHERE Employee.HireDate >= '2020-01-01'` filters individual employee rows before grouping.
- `GROUP BY Department.DeptName` collapses the remaining rows into one group per department.
- `COUNT(Employee.EmpID)` counts the employees in each group.
- `SUM(Employee.Salary)` totals the salaries in each group.
- `AVG(Employee.Salary)` computes the mean salary for each group.
- `ORDER BY ... DESC` sorts the output from the highest average to the lowest.

**Check.** In the 9618 subset, keep aggregate examples inside the listed DML features: use `WHERE` for row conditions before grouping, then `GROUP BY`, the aggregate function, and `ORDER BY` for the final sort.

## Example 8: DML UPDATE and DELETE

**Prompt.** Write SQL to (a) give every employee in department 3 a 5 percent pay rise, and (b) delete every employee hired before 2010.

**Solution.**

```sql
-- (a) 5 percent rise for department 3
UPDATE Employee
SET Salary = Salary * 1.05
WHERE DeptID = 3;

-- (b) remove employees hired before 2010
DELETE FROM Employee
WHERE HireDate < '2010-01-01';
```

- `UPDATE` changes existing rows. `SET` names the new value; `WHERE` restricts which rows are changed. Without a `WHERE`, every row would be updated.
- `DELETE FROM` removes rows that match the `WHERE`. Without `WHERE`, the whole table is emptied.
- The string `'2010-01-01'` is a date literal; comparing it to a `DATE` field selects the rows to remove.

**Check.** Always read the condition before running `UPDATE` or `DELETE`. Ask: "which rows does this `WHERE` select?" If the answer is "all rows" and that was not intended, the statement is wrong.

## Example 9: INSERT and a Simple SELECT

**Prompt.** Write SQL to insert a new department with ID 7 and name "Logistics", then write a query that lists the names and salaries of all employees in department 7, ordered alphabetically by name.

**Solution.**

```sql
INSERT INTO Department (DeptID, DeptName)
VALUES (7, 'Logistics');

SELECT EmpName, Salary
FROM Employee
WHERE DeptID = 7
ORDER BY EmpName ASC;
```

- `INSERT INTO` names the table and columns, then `VALUES` supplies the data in the same order.
- `SELECT` projects only the wanted columns (`EmpName`, `Salary`), `WHERE` filters to department 7, and `ORDER BY EmpName ASC` sorts A to Z.
- `ASC` is the default for `ORDER BY`, but stating it makes the intent clear.

**Check.** Match column count and types between the `INSERT INTO (...)` list and the `VALUES (...)` list. A `DATE` literal, an `INTEGER`, and a `VARCHAR` must line up with the order of columns.
