Pattern: Assigned function always returns `None`

Issue: -

## Description

Used when an assignment is done on a function call but the inferred function returns nothing but `None`. This may lead to confusion by readers and should be avoided. Remove assignment or update function to return not only 'None' to resolve this issue.


Example of **incorrect** code:
```python
def salute():
    print('hello')


def run():
    result = salute()
    print(result)
```

Example of **correct** code:
```python
def salute():
    return "hello"


def run():
    result = salute()
    print(result)
```
