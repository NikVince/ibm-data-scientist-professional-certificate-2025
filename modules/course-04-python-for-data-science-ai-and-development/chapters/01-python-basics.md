# Course 4, Module 1: Python Basics

This chapter solidified core Python primitives, expressions, variables, and strings—foundations for all subsequent data work.

## Data types and casting
- Integers: whole numbers (positive or negative)
- Floats: numbers with decimals; represent whole or fractional values
- Strings: quoted sequences of characters; ordered and indexable
- Booleans: `True`/`False`; `0 -> False`, non-zero -> `True`
- Typecasting: int <-> float; numbers -> string; numbers -> bool

## Expressions and operators
- Combine values and operators to produce a result
- Standard arithmetic (+, -, *, /), integer division `//` discards fractional part
- Python respects operator precedence (BODMAS)

## Variables
- Bind names to values using `=`
- Reassignment overrides the previous binding
- Arithmetic with variables uses current bound values
- Mutation affects other variables only if they reference the same mutable object

## Strings and text processing
- Declared with single or double quotes; sequences that support indexing and slicing
- Indices can be positive (from start) or negative (from end)
- Slicing with optional stride for stepping through characters
- Concatenation and replication create new strings; `len()` returns length
- Strings are immutable—operations create new strings rather than modifying in place
- Escape sequences change layout: `\n` new line, `\t` tab, `\\` backslash

## String methods (built-in)
- Case changes: `.lower()`, `.upper()`, `.title()`
- Search/replace: `.find()`, `.index()`, `.replace()`
- Trimming/splitting/joining: `.strip()`, `.split()`, `'sep'.join(list)`
- Formatting: `str.format()` and f-strings

## Takeaways
- Mastery of types, expressions, and strings enables reliable, readable Python code
- Prefer explicit casting and leverage string methods for robust text handling
