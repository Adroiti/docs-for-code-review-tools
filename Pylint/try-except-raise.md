Pattern: Redundant `raise` in `except`

Issue: -

## Description

Used when an except handler uses raise as its first or only operator. This is redundant because it raises back the exception immediately. Remove the raise operator or the entire `try-except-raise` block.