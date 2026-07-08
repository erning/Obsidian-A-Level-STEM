---
title: Databases Lecture Notes
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/08 Databases/00 Overview|Databases]]"
status: active
tags:
  - computerscience/data
  - lecture-notes
---

# Databases Lecture Notes

A database stores related data together so that it can be queried, kept consistent, and protected. This topic covers three layers that build on each other: the *concepts* of the relational model (why we abandon the file-based approach, and the precise vocabulary for entities, keys and relationships), the *software* that runs it (the DBMS and its tools), and the *language* used to define and manipulate data (SQL, split into DDL and DML). Each layer is examined in Paper 1, so the three must be learned as a connected whole rather than as separate facts.

## Source Route

- Syllabus **9618 AS Section 8 - Databases**.
- 8.1 Database Concepts: limitations of a file-based approach and how a relational database addresses them; relational terminology (entity, table, record, field, tuple, attribute, primary key, candidate key, secondary key, foreign key, relationship 1:1/1:M/M:N, referential integrity, indexing); entity-relationship (E-R) diagrams; normalisation to 1NF, 2NF, 3NF.
- 8.2 DBMS: features (data dictionary, data modelling, logical schema, data integrity, data security via backup and access rights) and tools (developer interface, query processor).
- 8.3 DDL and DML: DDL creates and modifies structure, DML queries and maintains data, SQL is the industry standard; DDL (CREATE DATABASE, CREATE TABLE with CHARACTER/VARCHAR(n)/BOOLEAN/INTEGER/REAL/DATE/TIME, ALTER TABLE, PRIMARY KEY, FOREIGN KEY ... REFERENCES); DML (SELECT ... FROM, WHERE, ORDER BY, GROUP BY, INNER JOIN, SUM, COUNT, AVG, INSERT INTO, DELETE FROM, UPDATE) across at most two tables.
- Assessed in **Paper 1**.

## 1. File-based approach and the relational fix

In a **file-based approach**, each application keeps its *own* set of files and writes its own code to read and write them. This sounds simple but creates well-known problems, which the relational database was invented to solve. Learn both the *problem* and the matching *feature*.

| Limitation of file-based approach | How a relational database addresses it |
| --- | --- |
| **Data duplication** - the same data (a customer's address) is typed into many files, wasting space and causing inconsistency when one copy is updated and another is not. | Data is stored *once* in a table and *referenced* by a key; the single copy is the source of truth. |
| **Data inconsistency** - because copies can disagree, no one knows which is correct. | One copy means one value; an update appears everywhere at once. |
| **Data dependence** - the file's physical format is hard-coded into the application, so changing the storage layout breaks the program. | The DBMS hides the physical storage behind a *logical schema*; the application works with tables, not files. |
| **Poor data integrity** - nothing stops an order from naming a customer that does not exist. | **Referential integrity**, enforced by the DBMS, blocks foreign keys that point at no real primary key. |
| **Lack of data sharing / concurrency** - one program locks the file, so another cannot work at the same time. | The DBMS manages concurrent access so many users share the data safely. |
| **No central security** - each file is protected (or not) by its own application. | The DBMS applies *access rights* and *backup* centrally, across all data. |

The shorthand answer is: a relational database reduces *duplication*, improves *integrity*, gives *data independence* (programs see tables, not physical files), allows *sharing*, and provides *centralised security and backup*. If a question asks "give one limitation of the file-based approach", pick one row and state both the limitation *and* how the relational model fixes it.

## 2. Relational terminology

The exam uses a precise vocabulary. Several terms are near-synonyms (entity ≈ table; tuple ≈ record; attribute ≈ field), so learn the conceptual word and the table word as a pair.

| Term | Meaning |
| --- | --- |
| **Entity** | A real-world "thing" the database models - a customer, an order, a part. Each entity becomes a *table*. |
| **Table (relation)** | A two-dimensional structure of rows and columns holding the data for one entity. |
| **Record (tuple)** | One *row* - all the data about a single instance of the entity, e.g. one customer. |
| **Field (attribute)** | One *column* - a single property stored for every record, e.g. `CustomerName`. |
| **Primary key (PK)** | An attribute (or set of attributes) that *uniquely identifies* a record and can never be null. There is exactly one per table. |
| **Candidate key** | *Any* attribute that could serve as the primary key - a field that is unique and non-null. One is chosen as the PK; the rest are alternate keys. |
| **Secondary key** | An attribute used frequently for *searching or sorting*, on which an index is built to speed up lookups (it is not unique). |
| **Foreign key (FK)** | An attribute in one table whose values *reference* the primary key of another table, creating the link between them. |
| **Relationship** | An association between two entities. Three types: **1:1** (one-to-one), **1:M** (one-to-many - the most common), **M:N** (many-to-many, always resolved via a *linking table*). |
| **Referential integrity** | A rule the DBMS enforces: a foreign key must either match an existing primary key in the referenced table or be null - it can never point to a record that does not exist. |
| **Indexing** | Building an extra data structure (like a book's index) on a field so records can be *found quickly* without scanning the whole table; speeds up search and sort at the cost of extra storage and slower writes. |

Two confusable pairs. **Primary key vs candidate key**: a candidate key is *any* unique non-null field; the primary key is the *one you choose*. **Secondary key vs foreign key**: a secondary key is for *fast searching within* a table; a foreign key is for *linking to* another table.

## 3. Entity-relationship (E-R) diagrams

An **E-R diagram** is a picture of the entities and their relationships, drawn *before* any tables or SQL. CAIE notation is simple and must be reproduced exactly.

| Element | Notation | Meaning |
| --- | --- | --- |
| **Entity** | A **rectangle** containing the entity name (e.g. `CUSTOMER`) | A "thing" - becomes a table |
| **Relationship** | A **line** joining two entities, with a verb label (e.g. `places`) | An association between entities |
| **Cardinality** | Symbols or numbers at each end of the line: `1`, `M`, or `N`; or crow's-foot marks | How many of each side take part (1:1, 1:M, M:N) |

To read a diagram, follow the line and read the cardinality at *each* end, naming the entity on that side. `CUSTOMER ---places--- ORDER` with a `1` at the customer end and `M` at the order end reads: **one** customer places **many** orders; each order belongs to exactly one customer - a one-to-many relationship.

To sketch a model:

1. Identify the **entities** (the nouns: customer, order, part) - draw a rectangle for each.
2. Draw the **lines** between them and write a **verb** on each line.
3. Add the **cardinality** at both ends (`1` / `M` / `N`).
4. For a **many-to-many** (M:N) relationship, never leave it as is: insert a **linking entity** (also called an intersection or bridge table) in the middle, which turns it into two one-to-many relationships. For example, `STUDENT` M:N `SUBJECT` becomes `STUDENT` 1:M `ENROLMENT` M:1 `SUBJECT`.

The cardinality and the linking-table rule are the two points most often examined; the shapes are always rectangle = entity, line = relationship.

## 4. Normalisation

**Normalisation** is the step-by-step process of restructuring a table to remove *redundancy* (repeated data) and *update anomalies*, producing a design that is efficient and free of inconsistency. There are three stages, each fixing a specific kind of problem. The definitions to learn are:

- **First normal form (1NF)** - no **repeating groups**; every field is *atomic* (holds a single value); each record has a primary key. Repeated columns are pulled out into separate rows or a new table.
- **Second normal form (2NF)** - already in 1NF, *and* every non-key attribute depends on the **whole** primary key, not just part of it. (This only matters when the key is **composite** - made of two or more fields. A table with a single-field key is automatically in 2NF if it is in 1NF.)
- **Third normal form (3NF)** - already in 2NF, *and* every non-key attribute depends on *nothing but* the primary key: there are no dependencies between non-key fields (no *transitive* dependency, such as `PostCode → City`).

The shorthand: "each non-key field must depend on **the key** (1NF), the **whole key** (2NF), and **nothing but the key** (3NF)". For an exam question of the form "is this table in 3NF?", check each rule in turn: are there repeating groups? does anything depend on only part of the key? does a non-key field depend on another non-key field? The first "yes" tells you the form it is in.

### Worked example: an invoice, unnormalised → 3NF

Start with one **unnormalised** view of an invoice, where each row repeats the customer and order details and lists all the parts on one line:

| InvoiceNo | CustomerID | CustomerName | OrderDate | PartNo | PartDescription | Qty | PartPrice |
| --- | --- | --- | --- | --- | --- | --- | --- |
| INV-01 | C100 | Acme | 2026-07-01 | P5, P7 | Bolt, Nut | 10, 4 | 0.20, 0.15 |
| INV-02 | C101 | Beta | 2026-07-01 | P5 | Bolt | 25 | 0.20 |

Problem: the `PartNo`, `PartDescription`, `Qty` and `PartPrice` fields each hold *multiple values* (a repeating group), so the row is not atomic.

**Step 1 - to 1NF.** Remove the repeating groups by giving every part its own row, and copy the invoice data down. Add a primary key.

1NF `INVOICE` (PK = `InvoiceNo, PartNo` - composite, because neither alone is unique):

| InvoiceNo | CustomerID | CustomerName | OrderDate | PartNo | PartDescription | Qty | PartPrice |
| --- | --- | --- | --- | --- | --- | --- | --- |
| INV-01 | C100 | Acme | 2026-07-01 | P5 | Bolt | 10 | 0.20 |
| INV-01 | C100 | Acme | 2026-07-01 | P7 | Nut | 4 | 0.15 |
| INV-02 | C101 | Beta | 2026-07-01 | P5 | Bolt | 25 | 0.20 |

No repeating groups; every field is atomic. But there is now heavy *duplication* (Acme and the date repeated) and *partial-key dependencies*: `CustomerID`, `CustomerName` and `OrderDate` depend only on `InvoiceNo`, while `PartDescription` and `PartPrice` depend only on `PartNo`.

**Step 2 - to 2NF.** Remove partial-key dependencies: each non-key field must depend on the *whole* key. Split into three tables.

`INVOICE` (PK = `InvoiceNo`):

| InvoiceNo | CustomerID | OrderDate |
| --- | --- | --- |
| INV-01 | C100 | 2026-07-01 |
| INV-02 | C101 | 2026-07-01 |

`PART` (PK = `PartNo`):

| PartNo | PartDescription | PartPrice |
| --- | --- | --- |
| P5 | Bolt | 0.20 |
| P7 | Nut | 0.15 |

`INVOICE_PART` (PK = `InvoiceNo, PartNo` - the linking table that was the original composite key):

| InvoiceNo | PartNo | Qty |
| --- | --- | --- |
| INV-01 | P5 | 10 |
| INV-01 | P7 | 4 |
| INV-02 | P5 | 25 |

Every non-key field now depends on the whole key of its table. `CustomerName` is left inside `INVOICE` at this stage - it depends on the whole key (a single field), so 2NF is satisfied, but there is still a hidden dependency.

**Step 3 - to 3NF.** Remove non-key to non-key (transitive) dependencies. In `INVOICE`, `CustomerName` depends on `CustomerID`, which is *not* the primary key - a transitive dependency. Split it out.

`CUSTOMER` (PK = `CustomerID`):

| CustomerID | CustomerName |
| --- | --- |
| C100 | Acme |
| C101 | Beta |

`INVOICE` (PK = `InvoiceNo`; `CustomerID` is now a **foreign key**):

| InvoiceNo | CustomerID | OrderDate |
| --- | --- | --- |
| INV-01 | C100 | 2026-07-01 |
| INV-02 | C101 | 2026-07-01 |

The final normalised design has four tables:

- `CUSTOMER` (**CustomerID**, CustomerName)
- `INVOICE` (**InvoiceNo**, CustomerID*(FK)*, OrderDate)
- `PART` (**PartNo**, PartDescription, PartPrice)
- `INVOICE_PART` (**InvoiceNo** *(FK)*, **PartNo** *(FK)*, Qty)

Every non-key field now depends on the key, the whole key, and nothing but the key; no data is duplicated except the keys used as foreign-key links. Notice how the many-to-many "an invoice contains many parts, a part appears on many invoices" was resolved by the linking table `INVOICE_PART` - the same idea as the E-R linking entity.

## 5. DBMS features and tools

A **database management system (DBMS)** is the software that sits between the users/applications and the stored data, providing the features and tools the file-based approach lacked.

**Features** (what the DBMS *provides*):

| Feature | What it does |
| --- | --- |
| **Data dictionary** | A store of *metadata* - descriptions of every table, field, type, key and relationship. The DBMS consults it to understand the structure of the database. |
| **Data modelling** | Support for designing the data structure (often via E-R diagrams) before implementation. |
| **Logical schema** | The *overall logical structure* of the database (tables, fields, keys, relationships), independent of how it is physically stored. This is what gives data independence. |
| **Data integrity** | Enforcement of rules that keep data correct - *entity integrity* (primary keys are unique and not null) and *referential integrity* (foreign keys must match an existing primary key or be null). Validation can also be defined. |
| **Data security** | Centralised protection of the data: **backup** (regular copies so data can be restored after loss) and **access rights** (each user/role is granted only the read/write/delete permissions they need). |

**Tools** (what the DBMS *exposes to the user/developer*):

| Tool | What it does |
| --- | --- |
| **Developer interface** | The environment through which a developer defines and maintains the database - writing DDL, designing the schema, and managing the structure. |
| **Query processor** | The component that takes a query (such as an SQL `SELECT`), parses and optimises it, works out how to execute it against the physical storage, and returns the result. It is what makes the logical schema usable without knowing the physical layout. |

The clean split is: *features* are capabilities the DBMS provides to keep data correct, independent and secure; *tools* are the interfaces that let humans and programs work with it.

## 6. SQL - DDL and DML

**SQL** is the industry-standard language for relational databases. It splits cleanly into two halves:

- **Data Definition Language (DDL)** - statements that *create or modify the structure* of the database (databases, tables, fields, types, keys). They change the *schema*, not the data.
- **Data Manipulation Language (DML)** - statements that *query or maintain the data* itself (retrieve, insert, update, delete rows). They change the *contents*, not the structure.

If a statement is about the shape of the database, it is DDL; if it is about the rows inside, it is DML.

### DDL - data definition

DDL statements and the SQL data types named in the syllabus:

| Statement / type | Purpose |
| --- | --- |
| `CREATE DATABASE` | Creates a new database. |
| `CREATE TABLE` | Creates a new table and its columns. |
| `ALTER TABLE` | Modifies an existing table's structure (add, drop or change a column; add a key). |
| `PRIMARY KEY (field)` | Declares the column (or columns) that uniquely identify a row. |
| `FOREIGN KEY (field) REFERENCES Table (Field)` | Declares a foreign key linking to another table's primary key. |
| `CHARACTER` | Fixed-length character string. |
| `VARCHAR(n)` | Variable-length character string, up to `n` characters. |
| `BOOLEAN` | Truth value (`TRUE` / `FALSE`). |
| `INTEGER` | Whole number. |
| `REAL` | Number with a fractional part (floating point). |
| `DATE` | Calendar date. |
| `TIME` | Time of day. |

Worked example - create the two related tables `CUSTOMER` and `INVOICE` from the normalised design, with a primary key and a foreign key:

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

The foreign key on `Invoice.CustomerID` references `Customer.CustomerID`; the DBMS will now enforce **referential integrity**, refusing any invoice whose `CustomerID` does not exist in `Customer`. To change a table after creation, use `ALTER TABLE`, e.g. to add a column: `ALTER TABLE Customer ADD CustomerEmail VARCHAR(60);` - this is DDL because it changes structure, not data.

### DML - data manipulation

DML statements and the clauses/functions named in the syllabus (queries span *at most two tables*):

| Clause / function | Purpose |
| --- | --- |
| `SELECT ... FROM` | Chooses the columns to output and the table(s) to read - the *projection*. |
| `WHERE` | Filters rows that satisfy a condition - the *selection*. |
| `ORDER BY` | Sorts the result rows (ascending or descending). |
| `GROUP BY` | Groups rows that share a value, so an *aggregate* can be computed per group. |
| `INNER JOIN` | Combines rows from two tables where the join condition matches (only matching rows appear). |
| `SUM` | Totals a numeric column. |
| `COUNT` | Counts rows (or non-null values). |
| `AVG` | Averages a numeric column. |
| `INSERT INTO` | Adds new rows. |
| `DELETE FROM` | Removes rows matching a condition. |
| `UPDATE` | Changes values in existing rows. |

Worked example - list, for each customer, the total quantity and average quantity they have ordered, but only for invoices since 1 July 2026, joining `Invoice` and `InvoicePart`. This uses `INNER JOIN`, `WHERE`, `GROUP BY` and two aggregates:

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

Read it in this order: which table(s) (`FROM` + `INNER JOIN`), which rows (`WHERE`), how they are grouped (`GROUP BY`), what is computed (`SUM`, `AVG`), and finally the sort (`ORDER BY`). A data-maintenance example: add a new part with `INSERT INTO Part (PartNo, PartDescription, PartPrice) VALUES ('P9', 'Washer', 0.05);`, remove a customer's invoices with `DELETE FROM Invoice WHERE CustomerID = 'C101';`, and raise a price with `UPDATE Part SET PartPrice = 0.25 WHERE PartNo = 'P5';`. All three are DML: they change *contents*, not structure.

## Worked-Thinking Routine

1. For a "limitations of file-based approach" question, name one limitation *and* how the relational model fixes it - one concrete sentence each.
2. For a terminology question, pair the conceptual word with the table word (entity/table, tuple/record, attribute/field) and state whether the key is for uniqueness (primary/candidate), linking (foreign) or fast searching (secondary).
3. For an E-R question, draw rectangles for entities, label the lines with verbs, and put cardinality at both ends; if you see many-to-many, insert a linking entity.
4. For a normalisation question, move one step at a time: 1NF removes repeating groups and gives a key; 2NF removes partial-key dependencies (check for composite keys); 3NF removes non-key-to-non-key dependencies. Show the resulting tables and underline each key.
5. For a DDL question, decide the tables, the columns and types, then the primary key, then any foreign key with its `REFERENCES`.
6. For a DML query, read it as table → join → filter → group → aggregate → sort, and write it in that order.

## Common Mistakes

- Listing only the limitation or only the fix. A file-based question needs both the problem *and* the relational feature that solves it.
- Confusing a **candidate key** (any unique non-null field) with the **primary key** (the one you chose).
- Treating a **secondary key** as a foreign key. A secondary key speeds up *searching within* a table; a foreign key *links to* another table.
- Drawing a many-to-many relationship and leaving it unresolved. M:N must always be split with a linking table.
- Stopping at 2NF when a non-key field still depends on another non-key field (e.g. `PostCode → City`).
- Forgetting that 2NF only matters for **composite** keys; a single-field-key table in 1NF is already in 2NF.
- Forgetting referential integrity when adding a foreign key - it must reference an existing primary key.
- Mixing **DDL** (structure: `CREATE`, `ALTER`) with **DML** (data: `SELECT`, `INSERT`, `UPDATE`, `DELETE`).
- Putting the join condition inside `WHERE` instead of `ON`, or omitting `ON` from an `INNER JOIN`.
- Using an aggregate (`SUM`, `COUNT`, `AVG`) without `GROUP BY` when the result needs per-group totals.

## Quick Self-Check

- Give one limitation of the file-based approach and the matching relational feature that fixes it.
- In one sentence each, define entity, table, record, field.
- Distinguish primary key, candidate key, secondary key and foreign key in one line each.
- Explain referential integrity and give an example of an insert it would block.
- Name the three relationship cardinalities and say which one requires a linking table.
- Sketch an E-R diagram for `STUDENT` M:N `SUBJECT` after resolving it to two one-to-many relationships.
- State the 1NF, 2NF and 3NF rules in the "key, whole key, nothing but the key" form.
- Take the worked invoice data and re-derive the four 3NF tables and all keys from memory.
- Explain why a table with a single-field primary key cannot fail 2NF.
- Write `CREATE TABLE` statements for two related tables with a primary key and a foreign key, using at least four different data types.
- Write an SQL query using `INNER JOIN`, `WHERE`, `GROUP BY` and `SUM`.
- In one sentence, separate the DBMS *features* from the DBMS *tools*, naming two of each.

## Connections

- [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/00 Overview|Security, Privacy and Data Integrity]] supplies the validation, access rights and backup concepts that appear here as DBMS data-integrity and data-security features.
- [[30 Computer Science/01 Topics/10 Data Types and Structures/00 Overview|Data Types and Structures]] shares the idea of structured records and field types, which reappear here as SQL data types and table columns.

## Study Sequence

1. Read this note top to bottom; then close it and write your own one-line definitions of entity, table, record and field from memory.
2. Memorise the file-based-limitations table until each "problem → fix" pair is automatic.
3. Drill the four key types (primary, candidate, secondary, foreign) and the three cardinalities, including the linking-table rule for M:N.
4. Re-derive the invoice normalisation from the unnormalised table to 3NF on a blank page, underlining every key.
5. Practise writing DDL for two related tables and DML with an `INNER JOIN` plus an aggregate until the keyword order is fluent.
6. Finish with the syllabus checklist: tick each "define", "explain" and "produce" point against what you can now do without notes.
