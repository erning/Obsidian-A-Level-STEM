---
title: Databases Review Checklist
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/08 Databases/00 Overview|Databases]]"
status: active
tags:
  - computerscience/data
  - review-checklist
---

# Databases Review Checklist

Use this as a self-test after reading the notes and attempting the practice problems. Keep answers out of sight until you can recall, design, normalise, and write SQL without prompting.

## Ideas to Recall

- [ ] Recall the limitations of a file-based approach and the matching relational-database fixes.
- [ ] Define entity, table, record, tuple, field, attribute, primary key, candidate key, secondary key, and foreign key.
- [ ] Distinguish primary keys, candidate keys, secondary keys, and foreign keys by purpose.
- [ ] Recall one-to-one, one-to-many, and many-to-many relationships.
- [ ] Explain referential integrity and indexing.
- [ ] Recall E-R notation: entity rectangles, relationship lines, verb labels, and cardinality.
- [ ] State the rules for 1NF, 2NF, and 3NF using "the key, the whole key, and nothing but the key".
- [ ] Recall DBMS features: data dictionary, data modelling, logical schema, data integrity, and data security.
- [ ] Recall DBMS tools: developer interface and query processor.
- [ ] Distinguish DDL from DML and recall the SQL statements, clauses, functions, and data types in this topic.

## Skills to Perform

- [ ] Explain a file-based limitation and the relational feature that solves it.
- [ ] Identify suitable primary, candidate, secondary, and foreign keys from a table description.
- [ ] Draw or describe an E-R diagram from a scenario and state cardinality at both ends.
- [ ] Resolve a many-to-many relationship by inserting a linking table.
- [ ] Normalise a table to 1NF, then 2NF, then 3NF, naming the dependency removed at each step.
- [ ] Decide whether a table is in 3NF and explain the first rule it fails.
- [ ] Write DDL to create related tables with data types, primary keys, and foreign keys.
- [ ] Write DML using `SELECT`, `FROM`, `WHERE`, `INNER JOIN`, `GROUP BY`, aggregate functions, and `ORDER BY`.
- [ ] Write `INSERT INTO`, `UPDATE`, and `DELETE FROM` statements with correct column lists and `WHERE` conditions.
- [ ] Read a SQL query in the order table, join, filter, group, aggregate, then sort.

## Things to Trace or Explain

- [ ] Trace how duplication in a file-based system leads to inconsistency.
- [ ] Explain how referential integrity blocks a foreign key that points to no real primary key.
- [ ] Trace an attempted parent-row deletion and explain reject, cascade, or nullify responses.
- [ ] Explain why a secondary key speeds searching but is not a link to another table.
- [ ] Trace a many-to-many relationship from E-R diagram to linking table with two foreign keys.
- [ ] Trace the invoice or order normalisation example from unnormalised data to final 3NF tables.
- [ ] Explain why 2NF only matters when the primary key is composite.
- [ ] Explain how a data dictionary differs from a logical schema.
- [ ] Connect this topic to [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/00 Overview|Security, Privacy and Data Integrity]] by explaining validation, backup, access rights, and integrity inside a DBMS.
- [ ] Connect this topic to [[30 Computer Science/01 Topics/10 Data Types and Structures/00 Overview|Data Types and Structures]] by explaining records, fields, and data types as structured data.

## Common Errors to Avoid

- [ ] Listing a file-based limitation without saying how the relational model fixes it.
- [ ] Confusing a candidate key with the primary key chosen from the candidate keys.
- [ ] Treating a secondary key as if it were a foreign key.
- [ ] Leaving a many-to-many relationship unresolved.
- [ ] Forgetting that a foreign key must reference an existing primary key.
- [ ] Stopping at 2NF while a non-key field still depends on another non-key field.
- [ ] Trying to find partial dependencies in a table with a single-field primary key.
- [ ] Mixing DDL structure statements with DML data statements.
- [ ] Omitting the `ON` condition from an `INNER JOIN`.
- [ ] Using aggregate functions for per-group results without `GROUP BY`.
- [ ] Writing `UPDATE` or `DELETE FROM` without checking which rows the `WHERE` clause selects.

## Ready to Move On When

- [ ] I can explain why relational databases reduce duplication and improve integrity compared with separate files.
- [ ] I can identify every key type in a small schema and say what each key is for.
- [ ] I can draw E-R relationships, resolve many-to-many links, and place foreign keys on the correct side.
- [ ] I can normalise a table to 3NF and explain each split using dependencies.
- [ ] I can distinguish DBMS features from DBMS tools.
- [ ] I can write two related `CREATE TABLE` statements with appropriate types and key constraints.
- [ ] I can write and read joined SQL queries with filters, grouping, aggregates, and sorting.
- [ ] I can connect database integrity and security back to [[30 Computer Science/01 Topics/06 Security, Privacy and Data Integrity/00 Overview|Security, Privacy and Data Integrity]].
- [ ] I can see how record structure connects databases to [[30 Computer Science/01 Topics/10 Data Types and Structures/00 Overview|Data Types and Structures]].
