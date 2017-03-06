Pattern: Duplicate key in dictionary

Issue: -

## Description

When dictionary key is redefined, it overwrites the key's value. This may lead to unexpected behavior and hard to detect bugs. Remove any duplicate keys to resolve this issue.


Example of **incorrect** code:

```python
wrong_dict = {
    'tea': 'for two',
    'two': 'for tea',
    'tea': 'time',

}
```

Example of **correct** code:

```python
correct_dict = {
    'tea': 'for two',
    'two': 'for tea',
}
```

## Further Reading

* [The Python Tutorial - Dictionaries](https://docs.python.org/2/tutorial/datastructures.html#dictionaries)
