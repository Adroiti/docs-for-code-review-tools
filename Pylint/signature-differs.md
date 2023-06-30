Pattern:  Child class method signature does not match parent class

Issue: -

## Description

Used when a method signature is different than in the implemented interface or in an overridden method.


Example of **incorrect** code:

```python
class Parent(object):

    def __init__(self):
        self.aarg = False

    def some_method(self, a=1):
        return a

class Child(Parent):

    def __init__(self, a):
        Parent.__init__(self)
        self.a = a

    def some_method(self, a): # [signature-differs]
        return a
```

Example of **correct** code:

```python
class Parent(object):

    def __init__(self):
        self.aarg = False

    def some_method(self, a=1):
        return a

class Child(Parent):

    def __init__(self, a):
        Parent.__init__(self)
        self.a = a

    def some_method(self, a=1):
        return a
```
