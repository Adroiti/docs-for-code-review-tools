Pattern: Redeclaring assigned name

Issue: -

## Description

Detects that a name was assigned one or multiple times in the same assignment, which indicate a potential bug.

Example of **incorrect** code:

```python
FIRST, FIRST = (1, 2)  # [redeclared-assigned-name]
```

Example of **correct** code:

```python
FIRST, SECOND = (1, 2)
```