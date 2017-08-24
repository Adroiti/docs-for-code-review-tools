Pattern: Unsubscriptable object

Issue: -

## Description

Emitted when a subscripted value doesn't support subscription (i.e. doesn't define `__getitem__` method).


Example of **incorrect** code:

```python
class NonSubscriptable(object):
    pass
    
NonSubscriptable()[0]  # [unsubscriptable-object]
NonSubscriptable[0]  # [unsubscriptable-object]
```

Example of **correct** code:

```python
class Subscriptable(object):
    def __getitem__(self, key):
        return key + key

Subscriptable()[0]
```

## Further Reading

* [The Python Language Reference - `__getitem__`](https://docs.python.org/2/reference/datamodel.html#object.__getitem__)
