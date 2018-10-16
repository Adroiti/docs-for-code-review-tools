Pattern: Missing use of `dict.get`

Issue: -

## Description

Using the builtin `dict.get` for getting a value from a dictionary if a key is present or a default if not, is simpler and considered more idiomatic, although sometimes a bit slower.

Example of **incorrect** code:

```python
dictionary = dict()
if 'key' in dictionary:
    variable = dictionary['key']
else:
    variable = 'default'
```

Example of **correct** code:

```python
variable = dictionary.get('key', 'default')
```

## Further Reading

* [The Python Standard Library - Mapping Types — dict](https://docs.python.org/3/library/stdtypes.html#dict.get)