Pattern: Unexpected special method signature

Issue: -

## Description

Emitted when a special method was defined with an invalid number of parameters. If it has too few or too many, it might not work at all.


Example of **incorrect** code:

```python
class Invalid(object):

    def __enter__(self, other):
        pass

    def __format__(self, other, other2):
        pass

    def __round__(self, invalid, args):
        pass
```

Example of **correct** code:

```python
class Valid(object):

    @staticmethod
    def __enter__():
        pass
        
    def __format__(self, format_specification=''):
        pass

    def __round__(self, n):
        pass
```

## Further Reading

* [The Python Language Reference - Special method names](https://docs.python.org/2/reference/datamodel.html#special-method-names)
