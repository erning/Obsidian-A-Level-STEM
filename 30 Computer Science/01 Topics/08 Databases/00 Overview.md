---
title: 08 Databases
subject: Computer Science
syllabus: 9618
status: active
tags:
  - computerscience/data
---

# 08 Databases

## Core Idea

A database stores related data so it can be queried, kept consistent, and protected. This topic covers the relational model, normalisation, the DBMS, and the SQL used to define and manipulate data.

## Source Alignment

- 9618 AS section 8 Databases
- 8.1 Database Concepts
- 8.2 Database Management Systems (DBMS)
- 8.3 Data Definition Language (DDL) and Data Manipulation Language (DML)
- Paper 1

## What to Learn

- Limitations of a file-based approach; how a relational database addresses them.
- Relational terminology: entity, table, record, field, tuple, attribute, primary key, candidate key, secondary key, foreign key, relationships (one-to-many, one-to-one, many-to-many), referential integrity, indexing.
- Entity-relationship (E-R) diagrams.
- Normalisation: 1NF, 2NF, 3NF; producing a normalised design; explaining whether given tables are in 3NF.
- DBMS features: data dictionary, data modelling, logical schema, data integrity, data security (backup, access rights).
- DBMS tools: developer interface, query processor.
- DDL: CREATE DATABASE, CREATE TABLE (with types CHARACTER, VARCHAR(n), BOOLEAN, INTEGER, REAL, DATE, TIME), ALTER TABLE, PRIMARY KEY, FOREIGN KEY ... REFERENCES.
- DML: SELECT ... FROM, WHERE, ORDER BY, GROUP BY, INNER JOIN, SUM, COUNT, AVG, INSERT INTO, DELETE FROM, UPDATE across at most two tables.

## How to Study

- Normalise from an unnormalised list step by step (1NF then 2NF then 3NF).
- Draw the E-R diagram before writing any SQL.
- Read SQL by identifying the target table, the join, the filter, and the projection.

## Practice Directions

- Normalise a given set of data to 3NF.
- Write DDL to create tables with primary and foreign keys.
- Write DML queries using SELECT, WHERE, INNER JOIN, ORDER BY, GROUP BY, and aggregate functions.

## Learning Materials

- [Lecture Notes](10%20Lecture%20Notes.md)
- [中文讲义](10%20Lecture%20Notes.zh-CN.md)
- [Worked Examples](20%20Worked%20Examples.md)
- [Key Practice Problems](30%20Key%20Practice%20Problems.md)
- [Key Practice Solutions](31%20Key%20Practice%20Solutions.md)
- [Review Checklist](80%20Review%20Checklist.md)

## Connections and Extensions

- [Security, Privacy and Data Integrity](../06%20Security%2C%20Privacy%20and%20Data%20Integrity/00%20Overview.md) supplies the validation, verification, access rights, backup, and integrity ideas that reappear as DBMS features.
- [Data Types and Structures](../10%20Data%20Types%20and%20Structures/00%20Overview.md) shares the idea of structured records, fields, data types, and relationships between stored values.
- [Software Development](../12%20Software%20Development/00%20Overview.md) connects database design to larger system work: requirements, data modelling, testing, and maintenance.
- [Ethics and Ownership](../07%20Ethics%20and%20Ownership/00%20Overview.md) adds the responsibility side of storing personal data, controlling access, and respecting ownership.

## Common Traps

- Stopping normalisation at 2NF when a partial-key dependency remains.
- Forgetting referential integrity when adding a foreign key.
- Mixing DDL (structure) and DML (data) statements.
