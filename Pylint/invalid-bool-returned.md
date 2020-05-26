Pattern: `__bool__` does not return bool

Issue: -

## Description

Used when a `__bool__` method returns something which is not a bool.

Example of **incorrect** code:

```python
class BadBool(object):
    """ __bool__ returns an integer """

    def __bool__(self):  # [invalid-bool-returned]
        return 1
```

Example of **correct** code:

```python
class GoodBool(object):
    """__bool__ returns <type 'bool'>"""

    def __bool__(self):
        return True
```