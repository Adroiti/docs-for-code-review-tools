Pattern: Unnecessary `else` after `break`

Issue: -

## Description

Used in order to highlight an unnecessary block of code following an `if` containing a `break` statement. As such, it will warn when it encounters an `else` following a chain of `if`s, all of them containing a `break` statement.

Example of **incorrect** code:

```python
def test(x, y, z):
    for i in x:
        if i > y:  # [no-else-break]
            break
        else:
            a = z
```

Example of **correct** code:

```python
def test(x, y, z):
    for i in x:
        if i > y:
            break
        return z
```