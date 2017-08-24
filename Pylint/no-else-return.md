Pattern: Unnecessary `else` after `return`

Issue: -

## Description

Used in order to highlight an unnecessary block of code following an `if` containing a `return` statement.
As such, it will warn when it encounters an `else` following a chain of `if`s, all of them containing a `return` statement.


Example of **incorrect** code:

```python
def test(x, y, z):
    if x:
        return y
    else:  # This is unnecessary here.
        return z
```

Example of **correct** code:

```python
def test(x, y, z):
    if x:
        return y
    return z
```
