# Course 6, Chapter 1: Basic SQL

## Overview
This chapter introduced core SQL concepts for reading and modifying relational data using Data Manipulation Language (DML) statements and common SELECT capabilities.

## Key Concepts
- DML statements read and modify data in tables.
  - INSERT: add new rows
  - UPDATE: change existing rows
  - DELETE: remove rows
- SELECT retrieves specific data from one or more tables.
  - WHERE clause refines results using predicates (conditions)
  - COUNT aggregates row counts; DISTINCT removes duplicates in result sets
  - LIMIT constrains the number of returned rows

## Practical Use Cases
- Filter customers by region or activity using WHERE conditions
- Count distinct users, products, or events with COUNT/DISTINCT
- Page through large results with LIMIT (and OFFSET)
- Populate tables with INSERT; correct data with UPDATE; clean up with DELETE

## Takeaways
- Combine SELECT with WHERE, DISTINCT, COUNT, and LIMIT to answer targeted questions efficiently.
- Use INSERT/UPDATE/DELETE responsibly with clear conditions and backups for safe modifications.
