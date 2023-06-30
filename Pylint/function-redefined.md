Pattern: Redefining function, class or method

Issue: -

## Description

Redefinition of functions, classes, and methods is allowed and overrides the original definition. This can make code hard to maintain and hard to read, and can cause subtle bugs when e.g. the wrong method is called. Update or remove redefined code or ignore this rule to resolve the issue.


Example of **incorrect** code:

```python
class A(object):
    def __init__(self):
        pass
        
    def method1(self):
        """docstring"""
        
    def method1(self): # [function-redefined]
        """docstring"""
```

Example of **correct** code:

```python
class A(object):
    def __init__(self):
        pass
        
    def method1(self):
```

