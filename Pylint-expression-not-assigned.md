Pattern: Expression not assigned

Issue: -

## Description

Used when an expression that is not a function call is assigned to nothing. Probably something else was intended.


Example of **incorrect** code:
```python
result == do_stuff() # [expression-not-assigned]
```

Example of **correct** code:
```python
result = do_stuff()
```
