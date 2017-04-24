Pattern: Object does not support item deletion

Issue: -

## Description

Used when an object does not support item deletion (i.e. doesn't define `__delitem__` method).


Example of **incorrect** code:

```python
class NonSubscriptable(object):
    pass

del NonSubscriptable()[0]
```

Example of **correct** code:

```python
class Subscriptable(object):
    def __delitem__(self, key):
        pass

del Subscriptable()[0]
```
