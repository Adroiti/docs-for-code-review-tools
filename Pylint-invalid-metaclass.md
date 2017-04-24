Pattern: Invalid metaclass used

Issue: -

## Description

Raised when a class is using an improper metaclass. This usually might indicate a problem in the code, rather than something done on purpose.


Example of **incorrect** code:

```python
# Needs to inherit from *type* in order to be valid
class SomeClass(object):
    ...

class CustomClass(metaclass=SomeClass):
    pass
```

Example of **correct** code:

```python
class SomeClass(type):
    ...

class CustomClass(metaclass=SomeClass):
    pass
```
