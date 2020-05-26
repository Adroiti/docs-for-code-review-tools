Pattern: `__format__` does not return string

Issue: -

## Description

Used when a `__format__` method returns something which is not a string.

Example of **incorrect** code:

```python
class BadFormat(object):
    """ __format__ returns bytes """

    def __format__(self, format_spec):  # [invalid-format-returned]
        return b"123"
```

Example of **correct** code:

```python
class GoodFormat(object):
    """__format__ returns <type 'str'>"""

    def __format__(self, format_spec):
        return "some format"
```