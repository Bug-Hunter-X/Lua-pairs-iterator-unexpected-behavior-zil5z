# Lua pairs iterator unexpected behavior

This repository demonstrates a potential issue with Lua's `pairs` iterator when used on tables that are modified during iteration.  The issue is subtle and can lead to unexpected behavior, including skipping elements or causing infinite loops.

## The Bug

The `bug.lua` file contains a function that recursively iterates through a nested table using `pairs`.  Under certain conditions (as shown in the example), the iterator may not correctly process all elements if the table structure is modified within the iteration.

## The Solution

The `bugSolution.lua` file offers a solution that uses a different approach to safely iterate over the nested table, ensuring all elements are processed correctly, even if the table structure is modified during the iteration. This solution uses an explicit stack-based approach for processing all sub-tables.