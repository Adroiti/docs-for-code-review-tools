Pattern: `__repr__` does not return string

Issue: -

## Description

Used when a `__repr__` method returns something which is not a string.

Example of **incorrect** code:

```python
class BadRepr(object):
    """ __repr__ returns bytes """

    def __repr__(self):  # [invalid-repr-returned]
        return b"123"
```

Example of **correct** code:

```python
class GoodRepr(object):
    """__repr__ returns <type 'str'>"""

    def __repr__(self):
        return "some repr"
```