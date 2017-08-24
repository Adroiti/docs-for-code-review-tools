Pattern: `self` not as first method argument

Issue: -

## Description

Used when the first argument of a (instance) method has a name other than `self`. 


This is nothing more than a convention: the name `self` has no special meaning to Python. Note, however, that by not following the convention your code may be less readable to other Python programmers, and it is also conceivable that a class browser program might be written that relies upon such a convention.


Example of **incorrect** code:

```python
class Felinae(object):
    def __init__(subfamily):
        self.subfamily = subfamily
```

Example of **correct** code:

```python
class Felinae(object):
    def __init__(self, subfamily):
        self.subfamily = subfamily
```

## Further Reading

* [PEP 8 - Function and method arguments](https://www.python.org/dev/peps/pep-0008/#function-and-method-arguments)
* [The Python Tutorial - Random Remarks](https://docs.python.org/2.7/tutorial/classes.html#random-remarks)
