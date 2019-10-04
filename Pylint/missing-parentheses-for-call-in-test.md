Pattern: Missing parentheses for call in condition

Issue: -

## Description

Emitted when a conditional statement (If or ternary if) seems to wrongly call a function due to missing parentheses.

Example of **incorrect** code:

```python
if bool_function: # [missing-parentheses-for-call-in-test]
    pass
```

Example of **correct** code:

```python
if not bool_function():
    pass
```
