Pattern: `__str__` does not return string

Issue: -

## Description

Used when a `__str__` method returns something which is not a string.

Example of **incorrect** code:

```python
class BadStr(object):
    """ __str__ returns bytes """

    def __str__(self):  # [invalid-str-returned]
        return b"123"
```

Example of **correct** code:

```python
class GoodStr(object):
    """__str__ returns <type 'str'>"""

    def __str__(self):
        return "some str"
```