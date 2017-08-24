Pattern: Use of verbose boolean return

Issue: -

## Description

This error occurs when you have an `if` statement that can be refactored by using the value of the condition, rather than putting in extra `True` and `False` literals. This makes the code more succinct and clear to the readers.


Example of **incorrect** code:

```python
def is_odd(num):
    if num % 2 != 0:
        return True
    else:
        return False
```

Example of **correct** code:

```python
def is_odd(num):
    return num % 2 != 0
```
