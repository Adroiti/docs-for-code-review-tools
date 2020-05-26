Pattern: `__hash__` does not return integer

Issue: -

## Description

Used when a `__hash__` method returns something which is not an integer.

Example of **incorrect** code:

```python
class BadHash(object):
    """ __hash__ returns a dict """

    def __hash__(self):  # [invalid-hash-returned]
        return {}
```

Example of **correct** code:

```python
class GoodHash(object):
    """__hash__ returns <type 'int'>"""

    def __hash__(self):
        return 1
```