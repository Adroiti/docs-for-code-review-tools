Pattern: Missing function docstring

Issue: -

## Description

Used when a function or method has no docstring. Some special methods like `__init__` do not require a docstring.

Example of **incorrect** code:

```python
def test(): # [missing-function-docstring]
    pass
```

Example of **correct** code:

```python
def test():
    """It has a docstring."""
```
