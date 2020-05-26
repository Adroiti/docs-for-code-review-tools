Pattern: `__length_hint__` does not return non-negative integer

Issue: -

## Description

Used when a `__length_hint__` method returns something which is not a non-negative integer.

Example of **incorrect** code:

```python
class BadLengthHint(object):
    """ __length_hint__ returns a negative integer """

    def __length_hint__(self):  # [invalid-length-hint-returned]
        return -1
```

Example of **correct** code:

```python
class GoodLengthHint(object):
    """__length_hint__ returns <type 'int'>"""

    def __length_hint__(self):
        return 0
```