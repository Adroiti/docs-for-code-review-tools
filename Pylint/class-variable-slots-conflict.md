Pattern: Conflict between class variable and slot name

Issue: -

## Description

Used when a value in `__slots__` conflicts with a class variable, property or method.

Example of **incorrect** code:

```python
class Bad(object):
    __slots__ = list
```

Example of **correct** code:

```python
class Good(object):
    __slots__ = ()
```