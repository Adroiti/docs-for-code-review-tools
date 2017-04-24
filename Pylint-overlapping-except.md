Pattern: Avoid overlapping exceptions

Issue: Name of found issue related to code. Use '-' to ignore if issue name is dynamic.

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
