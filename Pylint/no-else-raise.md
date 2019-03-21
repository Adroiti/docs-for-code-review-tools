Pattern: Unnecessary `else` after `raise`

Issue: -

## Description

Used in order to highlight an unnecessary block of code following an `if` containing a `raise` statement. As such, it will warn when it encounters an `else` following a chain of `if`s, all of them containing a `raise` statement.

Example of **incorrect** code:

```python
def test(x, y, z):
    if x:  # [no-else-raise]
        a = 1
        raise Exception(y)
    else:
        b = 2
        raise Exception(z)
```

Example of **correct** code:

```python
def test(x, y, z):
    if x:
        raise Exception(y)
    raise Exception(z)
```