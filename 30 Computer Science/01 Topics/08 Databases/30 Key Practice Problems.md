---
title: Databases Key Practice Problems
subject: Computer Science
syllabus: 9618
parent: "[[30 Computer Science/01 Topics/08 Databases/00 Overview|Databases]]"
status: active
tags:
  - computerscience/data
  - practice
---

# Databases Key Practice Problems

These problems cover the full AS Section 8 scope: relational concepts, normalisation, the DBMS, and SQL. Work them on paper before checking the [[30 Computer Science/01 Topics/08 Databases/31 Key Practice Solutions|solutions]]. No answers are given in this file.

## A. Relational Concepts

1. A clinic keeps patient details in a flat file and each receptionist keeps a separate copy of the same patient list. State two limitations of this file-based approach and explain how a relational database resolves each.

2. Define the following terms in one sentence each: entity, tuple, attribute, primary key, candidate key, foreign key.

3. A `Book` table has fields `ISBN`, `Title`, `AuthorID`, `Genre`, `PublishedYear`. State the most suitable primary key, name any other candidate key if one exists, and suggest one sensible secondary key. Justify each choice.

4. Explain the difference between a one-to-many and a many-to-many relationship. For each, give a real-world example and state which side holds the foreign key.

5. State what is meant by **referential integrity**, and describe two ways a DBMS could respond when a user tries to delete a row that is referenced by a foreign key.

6. Explain what an index is and give two reasons why indexing a secondary key can improve database performance, plus one disadvantage of having many indexes.

7. A library lends books to members. Each member can borrow many books; each book is borrowed by at most one member at a time; each book has exactly one author; each author may have written many books. Draw or describe an E-R diagram stating the entities, relationships, and cardinalities.

## B. Normalisation

8. Define what it means for a table to be in 1NF, in 2NF, and in 3NF. For 2NF and 3NF, state the type of dependency that must be removed.

9. The following unnormalised table records customer orders. Normalise it to 3NF, showing the result of each step and stating the primary key of every table.

   | OrderNo | CustID | CustName | ItemCode | ItemDesc | Qty | UnitPrice |
   |---------|--------|----------|----------|----------|-----|-----------|
   | 201     | C1     | Mia      | X1       | Cable    | 5   | 2.00      |
   | 201     | C1     | Mia      | X2       | Plug     | 3   | 1.00      |
   | 202     | C2     | Noor     | X1       | Cable    | 10  | 2.00      |

10. A `Project` table has fields `ProjectNo` (primary key), `ClientID`, `ClientName`, `StartDate`, `ManagerID`, `ManagerName`. The client name depends on the client ID, and the manager name depends on the manager ID. Explain why this table is not in 3NF and give the corrected 3NF design with all primary and foreign keys.

11. A `PupilLesson` table has fields `(PupilID, LessonID)` as primary key, plus `PupilName`, `LessonTime`, `Room`, `Subject`. Explain which of these fields cause a partial dependency and restructure the table into 2NF, then into 3NF.

12. A `Sale` table has fields `SaleID` (primary key), `ProductID`, `ProductName`, `CategoryID`, `CategoryName`. The product name depends on the product ID, and the category name depends on the category ID. Normalise to 3NF and state every key.

13. A classmate says "a table in 3NF is automatically in 2NF and 1NF". State whether this is true or false and justify your answer with reference to the definitions.

## C. DBMS

14. Name and briefly describe four features of a DBMS from the list: data dictionary, logical schema, data integrity, data security, developer interface, query processor.

15. Explain the difference between the **logical schema** and the **data dictionary** of a DBMS, and state one task each is used for.

16. Describe how a DBMS provides data security, referring to both backup and access rights, and state why each matters.

17. A database has an employee who tries to delete a department that still contains staff. Explain, using referential integrity, what the DBMS should do and why.

## D. SQL

18. Write SQL DDL to create a `Customer` table with fields `CustomerID` (integer, primary key), `CustomerName` (variable character up to 40), `Email` (variable character up to 60), and `Joined` (date).

19. Write SQL DDL to create an `Order` table related to `Customer`, with fields `OrderID` (integer, primary key), `OrderDate` (date), `CustomerID` (integer, foreign key referencing `Customer`). State which table must be created first and why.

20. Given `Order(OrderID, OrderDate, CustomerID)` and `OrderLine(OrderID, ProductID, Qty, LinePrice)`, write a query that lists, for each order, the order ID and the total value of its lines, ordered by total value descending.

21. Given `Customer(CustomerID, CustomerName, Joined)` and `Order(OrderID, OrderDate, CustomerID)`, write a query using `INNER JOIN` to list the name and order date of every customer who has placed at least one order, ordered by order date ascending.

22. Write SQL to increase by 10 percent the price of every order line for product `P5`, then delete every order line whose quantity is zero.

23. Write SQL to insert a new customer with ID 14, name "Sara", email "sara@example.com", joined today's date, and then write a query using `COUNT` and `GROUP BY` to show how many orders each customer has placed.

24. Write a query that uses `INNER JOIN`, `GROUP BY`, and `AVG` to show the average order value per customer, and explain in one sentence why `HAVING` rather than `WHERE` would be used to filter customers whose average is above a threshold.
