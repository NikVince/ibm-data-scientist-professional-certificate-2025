# Course 6, Chapter 4: Accessing Databases Using Python

## Overview
This chapter covered Python tools and patterns for connecting to databases, issuing queries, using cursors, and loading results into Pandas for analysis.

## Key Concepts
- Magic commands: special notebook commands; cell magics use `%%` and operate on multiple lines.
- DB APIs: Python Database API concepts center on Connection and Cursor (Query) objects.
- Connection object: establishes a session with the database (e.g., `sqlite3.connect(...)`).
- Cursor (query) object: control structure to execute SQL and traverse result records.
- Pandas integrates math/statistics helpers and can read structured files and SQL results.

## Practical Patterns
- Read CSVs: `pandas.read_csv("file.csv")` to import delimited data.
- Connect to SQLite: `conn = sqlite3.connect(db_path)`.
- Query with Pandas: `pd.read_sql("SELECT ...", conn)` to execute a SELECT and return a DataFrame.
- General flow:
  1) Create connection
  2) Create cursor (if using DB-API directly) and execute SQL
  3) Fetch results
  4) Load into Pandas for analysis (or use `pd.read_sql` directly)

## Takeaways
- Use notebook magics for convenience; use DB-API connections/cursors for programmatic control.
- `pd.read_sql` streamlines going from SQL to analysis-ready DataFrames.
