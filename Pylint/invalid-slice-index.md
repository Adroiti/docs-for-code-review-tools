Pattern: Invalid slice index

Issue: -

## Description

Used when a slice index is not an integer, `None`, or an object with an `__index__` method. This leads to unexpected behavior. Note that the slice numbers tell the start and stop positions for the slice in the list/tuple to get.


Example of **incorrect** code:
```python
list = ['t', 'e', 's', 't']
print(list['t': 's'])
```

Example of **correct** code:
```python
list = ['t', 'e', 's', 't']
print(list[0:3])
```

## Further Reading

* [The Python Standard Library - slice](https://docs.python.org/2/library/functions.html#slice)
