Pattern: Consider iterating dictionary

Issue: -

## Description

Emitted when the keys of a dictionary are iterated through the `.keys()` method. It is enough to just iterate through the dictionary itself, as in `for key in dictionary`.


Example of **incorrect** code:

```python
for key in dict.keys():
    print "{0} = {1}".format(key, dict[key])
```

Example of **correct** code:

```python
for key in dict:
    print "{0} = {1}".format(key, dict[key])
```

## Further Reading

* [The Python Tutorial - Dictionaries](https://docs.python.org/2/tutorial/datastructures.html#dictionaries)
