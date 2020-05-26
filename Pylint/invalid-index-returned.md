Pattern: `__index__` does not return integer

Issue: -

## Description

Used when an `__index__` method returns something which is not an integer.

Example of **incorrect** code:

```python
class BadIndex(object):
    """ __index__ returns a dict """

    def __index__(self):  # [invalid-index-returned]
        return {'1': '1'}
```

Example of **correct** code:

```python
class GoodIndex(object):
    """__index__ returns <type 'int'>"""

    def __index__(self):
        return 1
```