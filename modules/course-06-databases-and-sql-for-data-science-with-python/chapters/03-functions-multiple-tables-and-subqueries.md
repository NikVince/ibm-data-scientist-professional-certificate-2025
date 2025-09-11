# Course 6, Chapter 3: Functions, Multiple Tables, and Sub-queries

## Overview
This chapter highlighted the power of built-in database functions, writing queries over multiple tables, and composing sub-queries (including derived tables) to express richer logic efficiently.

## Key Concepts
- Built-in functions run inside the database engine, reducing data movement and speeding up operations on large datasets.
- Prefer pushing computation down to the database over retrieving raw data and post-processing in the application when possible.
- Sub-queries (sub-selects) enable more expressive queries by nesting SELECT statements inside other queries.
- Aggregate functions (e.g., `AVG`, `SUM`, `MIN`, `MAX`, `COUNT`) can be evaluated via sub-select expressions.
- Derived tables (table expressions) treat a sub-query's result set as a temporary table the outer query can join or filter over.

## Practical Examples
- Compute an average in a sub-select and compare each row to that average.
- Use a derived table to pre-aggregate facts, then join to dimensions for filtering and presentation.
- Apply built-in string/date/math functions directly in SELECT/WHERE/ORDER BY for performance and clarity.

## Takeaways
- Let the database do the heavy lifting: leverage built-in functions and sub-queries.
- Derived tables simplify complex logic and improve readability when composing multi-step transformations.
