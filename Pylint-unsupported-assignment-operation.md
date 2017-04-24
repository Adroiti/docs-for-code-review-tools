Pattern: Object does not support item assignment

Issue: -

## Description

Used when an object does not support item assignment (i.e. doesn't define `__setitem__` method).


Example of **incorrect** code:

```python
class NonSubscriptable(object):
    pass

NonSubscriptable()[0] = 1
```

Example of **correct** code:

```python
class Subscriptable(object):
    def __setitem__(self, key, value):
        return key + value
        
Subscriptable()[0] = 1
```
