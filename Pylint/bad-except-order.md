Pattern: Wrong order for `except` clauses

Issue: -

## Description

Used when except clauses are not in the correct order (from the more specific to the more generic). If you don't fix the order, some exceptions may not be caught by the most specific handler.


Example of **incorrect** code:

```python
try:
    __revision__ += 1
except LookupError:
    __revision__ = -1
except IndexError: # [bad-except-order]
    __revision__ = -2
```

Here warning is raised because `LookupError` is a base class for `IndexError` and is specified first. Example of **correct** code:

```python
try:
    __revision__ += 1
except IndexError:
    __revision__ = -1
except LookupError:
    __revision__ = -2
```

