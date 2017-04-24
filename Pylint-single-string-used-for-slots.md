Pattern: Class `__slots__` should be a non-string iterable

Issue: -

## Description

Used when a class `__slots__` is a simple string, rather than an iterable.


Example of **incorrect** code:

```python
from collections import deque

class Bad(object):
    __slots__ = deque.__name__
```

Example of **correct** code:

```python
from collections import deque

class PotentiallyGood(object): # [invalid-slots]
    __slots__ = ('a', deque.__name__)
```
