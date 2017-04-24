Pattern: Redefining argument with the local name

Issue: -

## Description

Used when a local name is redefining an argument, which might suggest a potential error. 
This is taken in account only for a handful of name binding operations, such as `for` iteration, `with` statement assignment and exception handler assignment.


Example of **incorrect** code:
```python
def test_redefined_in_with(name):
    with open('something') as name:
        pass
```

Example of **correct** code:

```python
def test_not_redefined_in_with(name):
    other = None
    with open('something') as other:
        pass
```
