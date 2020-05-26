Pattern: `__bytes__` does not return bytes

Issue: -

## Description

Used when a `__bytes__` method returns something which is not bytes.

Example of **incorrect** code:

```python
class BadBytes(object):
    """ __bytes__ returns bytes """

    def __bytes__(self):  # [invalid-bytes-returned]
        return "123"
```

Example of **correct** code:

```python
class GoodBytes(object):
    """__bytes__ returns <type 'bytes'>"""

    def __bytes__(self):
        return b"some bytes"
```