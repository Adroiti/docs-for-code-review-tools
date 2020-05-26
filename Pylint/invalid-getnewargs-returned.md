Pattern: `__getnewargs__` does not return tuple

Issue: -

## Description

Used when a `__getnewargs__` method returns something which is not a tuple.

Example of **incorrect** code:

```python
class BadGetNewArgs(object):
    """ __getnewargs__ returns an integer """

    def __getnewargs__(self):  # [invalid-getnewargs-returned]
        return 1
```

Example of **correct** code:

```python
class GoodGetNewArgs(object):
    """__getnewargs__ returns <type 'tuple'>"""

    def __getnewargs__(self):
        return (1, "2", 3)
```