Pattern: Too many function arguments

Issue: -

## Description

Calls to function with mismatched number of arguments will raise a runtime error and are usually a result of incomplete refactoring. Update code so that arguments are matched.


Example of **incorrect** code:
```python
def get_sum(x, y):
    return x + y

get_sum(1, 2, 3)  # Error on this line
```

Example of **correct** code:
```python
def get_sum(x, y):
    return x + y

get_sum(1, 2)
```
