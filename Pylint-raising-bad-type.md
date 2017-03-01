Pattern: Raising bad type

Issue: -

## Description

Used when something which is neither a class, an instance or a string is raised (i.e. a `TypeError` will be raised).


Example of **incorrect** code:

```python
def bad_case():
    """raise"""
    raise 1  # [raising-bad-type]

```

Example of **correct** code:

```python
def good_case():
    """raise"""
    raise ValidException('error details')
```

## Further Reading

* [Pylint - E0702](http://pylint-messages.wikidot.com/messages:e0702)
