Pattern: Unnecessary `else` after `continue`

Issue: -

## Description

Used in order to highlight an unnecessary block of code following an `if` containing a `continue` statement. As such, it will warn when it encounters an `else` following a chain of `if`s, all of them containing a `continue` statement.

Example of **incorrect** code:

```python
def test(x, y, z):
    for i in x:
        if i < y:  # [no-else-continue]
            continue
        else:
            a = z
```

Example of **correct** code:

```python
def test(x, y, z):
    for i in x:
        if i < y:
            continue
        return z
```
