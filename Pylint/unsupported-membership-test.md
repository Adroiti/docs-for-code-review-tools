Pattern: Unsupported membership test

Issue: -

## Description

If you use membership test `a in b` but the `b`'s type does not support this type of check, then a runtime error is raised. The standard Python types which support this check are strings, lists, tuples, and dictionaries.


Example of **incorrect** code:
```python
item = 123
if 'a' in list:
    print('unsupported membership test')
```

Example of **correct** code:
```python
item = "abc"
if 'a' in list:
    print('supported membership test')
```

## Further Reading

* [The Python Standard Library - Iterator Types](https://docs.python.org/2/library/stdtypes.html#iterator-types)
