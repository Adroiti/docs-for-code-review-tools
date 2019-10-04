Pattern: Missing class docstring

Issue: -

## Description

Used when a class has no docstring. Even an empty class should have a docstring.

Example of **incorrect** code:

```python
class Test(object): # [missing-class-docstring]
    pass
```

Example of **correct** code:

```python
class Test(object):
    """It has a docstring."""
```
