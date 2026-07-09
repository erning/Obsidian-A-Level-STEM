---
title: Databases Key Practice Solutions
subject: Computer Science
syllabus: 9618
parent: "[Databases](00%20Overview.md)"
status: active
tags:
  - computerscience/data
  - solutions
---

# Databases Key Practice Solutions

Full working for every problem in [Databases Key Practice Problems](30%20Key%20Practice%20Problems.md). Normalised designs state the primary key (PK) and foreign keys (FK) of every table; SQL appears in fenced code blocks.

## A. Relational Concepts

### 1. File-based limitations and the relational fix

- **Data duplication**: the patient list is copied in each receptionist's file, wasting storage. Relational fix: store patient data once in a `Patient` table; every user references the patient by its primary key, so the data exists in only one place.
- **Data inconsistency**: if one receptionist updates an address and another does not, the copies disagree. Relational fix: a single shared table means an update is applied once and every user sees the same value immediately.
- A further limitation is **no controlled concurrent access or rights management**; a DBMS provides a single store with per-user access rights and backup.

### 2. Definitions

- **Entity**: a real-world object about which data is stored, such as a customer or order. It becomes a table.
- **Tuple**: a single row in a table, representing one record.
- **Attribute**: a single column in a table, representing one property of the entity.
- **Primary key**: an attribute (or set of attributes) that uniquely identifies each tuple and is not null.
- **Candidate key**: any attribute that could uniquely identify each tuple and so could be chosen as the primary key.
- **Foreign key**: an attribute in one table whose values match the primary key of another table, used to represent a relationship.

### 3. Keys in the `Book` table

- **Primary key**: `ISBN`. It is unique for every book and never null.
- **Candidate key**: there is no obvious second unique field; `Title` can repeat across editions, so the only candidate key is `ISBN`.
- **Secondary key**: `Title` or `Genre`. These are non-unique but commonly searched or ordered on, so indexing them speeds up `WHERE` and `ORDER BY` lookups.

### 4. One-to-many vs many-to-many

- **One-to-many (1:M)**: one parent row matches many child rows, but each child has exactly one parent. Example: one `Customer` places many `Order`s; each order belongs to one customer. The foreign key sits on the "many" side (`Order.CustomerID` references `Customer`).
- **Many-to-many (M:N)**: rows on each side can match many rows on the other. Example: a `Student` is enrolled on many `Course`s, and a `Course` has many students. A relational design cannot store this directly; it needs a **link table** (for example `Enrolment`) holding the two primary keys as foreign keys.

### 5. Referential integrity

Referential integrity means that every foreign key value must either match an existing primary key value in the referenced table or be null. When a user tries to delete a referenced row, the DBMS may:

- **Reject** the deletion, leaving the parent row in place.
- **Cascade** the deletion, automatically deleting the dependent rows (the children vanish with the parent).
- **Nullify** the foreign key in dependent rows (only if the foreign key allows null).

### 6. Indexes

An index is an auxiliary data structure, typically a tree, built on one or more columns, that lets the DBMS find matching rows without scanning the whole table.

- It speeds up `WHERE` lookups on the indexed column.
- It speeds up `ORDER BY` and `JOIN` operations on the indexed column.
- Disadvantage: each extra index adds storage and slows down `INSERT`, `UPDATE`, and `DELETE`, because the index must be kept up to date on every change.

### 7. E-R diagram for the library

- Entities: `Member`, `Book`, `Author`.
- `Member` borrows `Book`: **one-to-many (1:M)**, since each book is borrowed by at most one member at a time, but a member may borrow many books. Foreign key on the `Book` side.
- `Author` writes `Book`: **one-to-many (1:M)**, since each book has one author but an author may have written many books. Foreign key on the `Book` side.

The diagram reads: `Member` -1:M- `Book` -M:1- `Author`.

## B. Normalisation

### 8. Definitions of the normal forms

- **1NF**: every attribute is atomic (no repeating groups, no multi-valued cells); there is a primary key.
- **2NF**: 1NF plus no **partial dependency**. Every non-key attribute must depend on the whole primary key, not on part of a composite key.
- **3NF**: 2NF plus no **transitive dependency**. Every non-key attribute must depend on nothing but the primary key (no `Key -> X -> Y` where `X` is not a key).

### 9. Normalising the order table

Step to **1NF**: the cells are atomic and the key is the composite `(OrderNo, ItemCode)`.

Step to **2NF**: remove partial dependencies.

- `ItemDesc` and `UnitPrice` depend only on `ItemCode`.
- `CustID` and `CustName` depend only on `OrderNo`.
- `Qty` depends on the whole key.

Result:

- `Order(OrderNo, CustID)` - PK `OrderNo`.
- `OrderItem(OrderNo, ItemCode, Qty)` - PK `(OrderNo, ItemCode)`, FK `OrderNo` references `Order`, FK `ItemCode` references `Item`.
- `Item(ItemCode, ItemDesc, UnitPrice)` - PK `ItemCode`.

Step to **3NF**: in `Order`, `CustName` depends on `CustID`, a non-key attribute, so split `Customer` out.

Final design:

- `Order(OrderNo, CustID)` - PK `OrderNo`, FK `CustID` references `Customer`.
- `Customer(CustID, CustName)` - PK `CustID`.
- `OrderItem(OrderNo, ItemCode, Qty)` - PK `(OrderNo, ItemCode)`, FKs to `Order` and `Item`.
- `Item(ItemCode, ItemDesc, UnitPrice)` - PK `ItemCode`.

### 10. `Project` table not in 3NF

Two transitive dependencies break 3NF:

- `ClientID -> ClientName` (client name depends on client ID, a non-key attribute).
- `ManagerID -> ManagerName` (manager name depends on manager ID, a non-key attribute).

Corrected 3NF design:

- `Project(ProjectNo, ClientID, ManagerID, StartDate)` - PK `ProjectNo`, FK `ClientID` references `Client`, FK `ManagerID` references `Manager`.
- `Client(ClientID, ClientName)` - PK `ClientID`.
- `Manager(ManagerID, ManagerName)` - PK `ManagerID`.

### 11. `PupilLesson` partial and transitive dependencies

The composite key is `(PupilID, LessonID)`. Partial dependencies: `PupilName` depends only on `PupilID`, and `LessonTime`, `Room`, `Subject` depend only on `LessonID`.

**To 2NF** (remove partial dependencies):

- `Pupil(PupilID, PupilName)` - PK `PupilID`.
- `Lesson(LessonID, LessonTime, Room, Subject)` - PK `LessonID`.
- `PupilLesson(PupilID, LessonID)` - PK `(PupilID, LessonID)`, FKs to `Pupil` and `Lesson`.

**To 3NF**: check each table for transitive dependencies. If `Subject` is determined by `Room` (for example, each room is a fixed subject lab), then `Room -> Subject` is transitive and `Subject` moves to a `Room` table. Otherwise the 2NF design above is already in 3NF.

### 12. `Sale` table normalised

- `Sale(SaleID, ProductID)` - PK `SaleID`, FK `ProductID` references `Product`.
- `Product(ProductID, ProductName, CategoryID)` - PK `ProductID`, FK `CategoryID` references `Category`.
- `Category(CategoryID, CategoryName)` - PK `CategoryID`.

`ProductName` depends on `ProductID` (so it moves with the product), and `CategoryName` depends on `CategoryID`, a non-key attribute, so it forms its own `Category` table.

### 13. "3NF implies 2NF and 1NF"

True. The normal forms are cumulative: 2NF requires 1NF first, and 3NF requires 2NF first. So a table in 3NF has no partial dependencies (so it is in 2NF) and no repeating groups (so it is in 1NF). A table that fails 1NF or 2NF cannot be in 3NF.

## C. DBMS

### 14. Four DBMS features

- **Data dictionary**: stores metadata about every table, attribute, type, and key, so the structure of the database is self-describing.
- **Logical schema**: the formal description of the tables, attributes, keys, and relationships, independent of how data is physically stored.
- **Data integrity**: built-in rules such as primary key uniqueness, type checks, and referential integrity that keep data consistent.
- **Query processor**: accepts SQL statements, checks and optimises them, and executes them against the stored data, returning results to the user or application.

### 15. Logical schema vs data dictionary

The **logical schema** is the designer's description of the tables and relationships: what entities exist, what attributes they have, and how they relate. It is used to design and reason about the database.

The **data dictionary** is the stored catalogue the DBMS itself maintains: it records, for each table and column, the name, data type, key role, and constraints. It is used by the DBMS to validate and process operations, and by developers to inspect the live structure.

### 16. Data security

- **Backup**: the DBMS can take periodic copies of the data so that, after hardware failure or accidental deletion, the database can be restored to a known state. Without backups, a single failure can lose all data.
- **Access rights**: the DBMS controls which users can read, insert, update, or delete which tables. This prevents unauthorised viewing or modification, and limits the damage if a single account is compromised.

Both matter because data has value and is shared: backups protect against loss, and access rights protect against misuse.

### 17. Deleting a department that still has staff

Referential integrity forbids leaving foreign keys pointing at rows that no longer exist. The DBMS must therefore not simply delete the department and leave dangling `DeptID` values in `Employee`. Depending on the rule set when the foreign key was defined, the DBMS will:

- reject the deletion and leave the department intact (the safe default), or
- cascade the deletion, removing the staff rows as well, or
- set the staff rows' `DeptID` to null, if the foreign key allows it.

The purpose is to keep the relationship valid: every employee must still belong to a real department.

## D. SQL

### 18. DDL for `Customer`

```sql
CREATE TABLE Customer (
    CustomerID    INTEGER,
    CustomerName  VARCHAR(40),
    Email         VARCHAR(60),
    Joined        DATE,
    PRIMARY KEY (CustomerID)
);
```

### 19. DDL for `Order` related to `Customer`

```sql
CREATE TABLE Order (
    OrderID     INTEGER,
    OrderDate   DATE,
    CustomerID  INTEGER,
    PRIMARY KEY (OrderID),
    FOREIGN KEY (CustomerID) REFERENCES Customer(CustomerID)
);
```

`Customer` must be created first, because the foreign key in `Order` references the primary key of `Customer`. If `Customer` did not exist, the `REFERENCES` clause would fail.

### 20. Total value per order

```sql
SELECT OrderID, SUM(LinePrice)
FROM OrderLine
GROUP BY OrderID
ORDER BY SUM(LinePrice) DESC;
```

### 21. Customers and their orders, using INNER JOIN

```sql
SELECT Customer.CustomerName, Order.OrderDate
FROM Customer
INNER JOIN Order ON Customer.CustomerID = Order.CustomerID
ORDER BY Order.OrderDate ASC;
```

### 22. Update price for product P5, delete zero-quantity lines

```sql
UPDATE OrderLine
SET LinePrice = LinePrice * 1.10
WHERE ProductID = 'P5';

DELETE FROM OrderLine
WHERE Qty = 0;
```

### 23. Insert a customer and count orders per customer

```sql
INSERT INTO Customer (CustomerID, CustomerName, Email, Joined)
VALUES (14, 'Sara', 'sara@example.com', '2026-07-08');

SELECT CustomerID, COUNT(OrderID)
FROM Order
GROUP BY CustomerID;
```

### 24. Average order value per customer with INNER JOIN

```sql
SELECT Customer.CustomerID, Customer.CustomerName, AVG(Order.TotalValue)
FROM Customer
INNER JOIN Order ON Customer.CustomerID = Order.CustomerID
WHERE Order.OrderDate >= '2026-01-01'
GROUP BY Customer.CustomerID, Customer.CustomerName
ORDER BY AVG(Order.TotalValue) DESC;
```

The `INNER JOIN` matches customers to their orders, `WHERE` keeps only orders on or after 1 January 2026, `GROUP BY` creates one group per customer, and `AVG(Order.TotalValue)` calculates the mean order value for each group.
