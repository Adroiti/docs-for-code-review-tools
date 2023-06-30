Pattern: Use of `self` or `cls` as first static method argument

Issue: -

## Description

Because it is customary for instance or class methods to take `self` or `cls`, respectively, as their first arguments, a method that uses either of these names but is found to be a static method may have been defined incorrectly.


Even if the method being flagged is truly meant to be a static method, you should be mindful of the convention above and choose names other than `self` or `cls` for arguments. Otherwise you risk confusing other Python programmers looking at your code.


Example of **incorrect** code:

```python
class Test(object):
    @staticmethod
    def add1(self):
        print "called add1"
        
    @staticmethod
    def add2(cls):
        print "called add2"
```

Example of **correct** code:

```python
class Test(object):
    @staticmethod
    def add1():
        print "called add1"
        
    @staticmethod
    def add2():
        print "called add2"
```

