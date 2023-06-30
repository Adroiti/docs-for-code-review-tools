Pattern: Returning a value from `__init__`

Issue: -

## Description

Because `__new__()` and `__init__()` work together in constructing objects, no non-`None` value may be returned by `__init__()`; doing so will cause a `TypeError` to be raised at runtime.


Example of **incorrect** code:
```python
class Felinae:
    def __init__(self, subfamily):
        self.subfamily = subfamily
        return self.subfamily
```

Example of **correct** code:
```python
class Felinae:
    def __init__(self, subfamily):
        self.subfamily = subfamily
```

## Further Reading

* [The Python Language Reference - `__init__`](https://docs.python.org/2/reference/datamodel.html#object.__init__)
