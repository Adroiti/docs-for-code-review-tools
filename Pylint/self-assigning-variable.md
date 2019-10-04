Pattern: Assigning variable to itself

Issue: -

## Description

Detects that a variable is assigned to itself, which might indicate a potential bug in the code application.

Example of **incorrect** code:

```python
FIRST = 1
FIRST = FIRST # [self-assigning-variable]
```

Example of **correct** code:

```python
FIRST = 1
```