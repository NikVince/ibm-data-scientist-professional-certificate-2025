# Course 6, Chapter 2: Relational Database Concepts and Tables

## Overview
This chapter introduced foundational relational database concepts, why the relational model is widely used, and how SQL categories map to creating and manipulating data.

## Key Concepts
- Databases are repositories that support adding, modifying, and querying data.
- SQL is the language used to query (retrieve) and manipulate data in relational databases.
- The Relational Model is popular due to data independence (logical vs. physical separation), enabling portability and maintainability.
- Primary Keys uniquely identify each row (tuple) in a table, prevent duplicates, and enable defining relationships across tables (via foreign keys).
- SQL categories:
  - DDL (Data Definition Language): defines and alters schema objects (e.g., CREATE, ALTER, DROP)
  - DML (Data Manipulation Language): reads and modifies data (e.g., SELECT, INSERT, UPDATE, DELETE)

## Takeaways
- Use primary keys to ensure entity integrity and support relational links.
- Separate concerns: use DDL for schema changes and DML for data access and updates.
