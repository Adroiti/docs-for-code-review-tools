Pattern: Return iterator in `__iter__`

Issue: -

## Description

Used when an `__iter__` method returns something which is not an iterable (i.e. has no `next` method). A container must implement an `__iter__` method that returns an iterator object, otherwise Python will raise the `TypeError: __iter__ returned non-iterator of type %r`.


Example of **incorrect** code:
```python
class GoodIterator(object):
    """ yields in iterator. """

    def __iter__(self):
        for index in range(10):
            yield index
```

Example of **correct** code:
```python
class BadIterator(object):
    """ __iter__ returns a list """

    def __iter__(self): # [non-iterator-returned]
        return []
```

## Further Reading

* [The Python Standard Library - Iterator Types](https://docs.python.org/2/library/stdtypes.html#iterator-types)
