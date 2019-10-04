Pattern: Missing use of `sys.exit()`

Issue: -

## Description

Instead of using `exit()` or `quit()`, consider using the `sys.exit()`.

Example of **incorrect** code:

```python
def test():
    exit()
```

Example of **correct** code:

```python
def test():
    sys.exit()
```

