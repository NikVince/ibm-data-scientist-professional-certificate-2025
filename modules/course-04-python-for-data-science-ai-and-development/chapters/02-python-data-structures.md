# Course 4, Module 2: Python Data Structures

This chapter explored Python's core collection types—tuples, lists, dictionaries, and sets—essential for organizing and manipulating data efficiently.

## Tuples
- Ordered, immutable collections of elements enclosed in parentheses `()`
- Can contain mixed data types (strings, integers, floats)
- Support positive and negative indexing for element access
- Allow operations like concatenation and slicing
- Support nesting of tuples within tuples
- Immutability requires creating new tuples for any changes

## Lists
- Ordered, mutable sequences enclosed in square brackets `[]`
- Store elements of different types, including nested lists
- Support positive and negative indexing like tuples
- Allow in-place modifications through methods like `.append()` and `.remove()`
- Can be concatenated, sliced, and split using delimiters
- Present aliasing challenges when multiple variables reference the same list
- Support cloning to create independent copies

## Dictionaries
- Key-value pairs enclosed in curly braces `{}`
- Keys must be unique and immutable
- Values can be mutable or immutable and allow duplicates
- Support operations for adding, retrieving, and deleting entries
- Provide methods to check for key existence (returning boolean)
- Include functions to extract lists of keys and values

## Sets
- Unordered collections of unique elements
- Defined using curly braces `{}` or the `set()` constructor
- Automatically eliminate duplicates when created from other collections
- Support mathematical set operations:
  - Addition/removal of elements
  - Intersection with `&` operator to find common elements
  - Union to combine sets with both common and unique elements
  - Subset testing to determine containment relationships

## Takeaways
- Each collection type serves specific purposes in data organization
- Understand mutability differences to avoid unexpected behavior
- Choose the appropriate structure based on access patterns and operations needed
- Master collection manipulations for efficient data preprocessing in data