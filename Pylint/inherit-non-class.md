Pattern: Inheritance from non-class

Issue: -

## Description

Used when a class inherits from something which is not a class. Python will raise an exception on runtime and program will not execute.


Example of **incorrect** code:

```python
class Bad(1): # [inherit-non-class]
    """ Can't inherit from instance. """
```

Example of **correct** code:

```python
class Good(object):
    pass
```

## Further Reading

* [The Python Tutorial - Inheritance](https://docs.python.org/2/tutorial/classes.html)
