Pattern: `NotImplemented` raised instead of `NotImplementedError`

Issue: -

## Description

`NotImplemented` is is a built-in constant used to indicate that the comparison is not implemented with respect to the other type. `NotImplementedError` is an exception used to indicate some module functionality is not implemented.


Example of **incorrect** code:

```python
def bad_case():
    raise NotImplemented  # [notimplemented-raised]
```

Example of **correct** code:

```python
def good_case():
    raise NotImplementedError
```

## Further Reading

* [The Python Standard Library - NotImplemented](https://docs.python.org/2/library/constants.html#NotImplemented)
* [The Python Standard Library - NotImplementedError](https://docs.python.org/2/library/exceptions.html#exceptions.NotImplementedError)
