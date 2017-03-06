Pattern: Iterable is expected but not used

Issue: -

## Description

When a non-iterable value is used in place where iterable is expected, a runtime error is raised. Remove it's use or update code to return an iterable.


Example of **incorrect** code:
```python
for i in 8.5:
    print i
```

Example of **correct** code:
```python
for i in range(1, 10):
    print i
```

## Further Reading

* [The Python Standard Library - Iterator Types](https://docs.python.org/2/library/stdtypes.html#iterator-types)
