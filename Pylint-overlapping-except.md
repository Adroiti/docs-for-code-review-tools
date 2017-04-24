Pattern: Avoid overlapping exceptions

Issue: -

## Description

Used when exceptions in handler overlap or are identical.


Example of **incorrect** code:

```python
class SomeException(Exception):
    pass


try:
    pass
except (SomeException, SomeException):
    pass
```

Example of **correct** code:

```python
class SomeException(Exception):
    pass


try:
    pass
except (SomeException):
    pass
```
