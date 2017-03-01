Pattern: Missing method argument

Issue: -

## Description

Used when a method which should have the bound instance as first argument has no argument defined. Consider adding `self` parameter to such methods to resolve this issue.


Example of **incorrect** code:

```python
class Felinae(object):
    def __init__(self, subfamily):
        self.subfamily = subfamily

    def hunt(): # [no-method-argument]
        print("hunting") 
```

Example of **correct** code:

```python
class Felinae(object):
    def __init__(self, subfamily):
        self.subfamily = subfamily

    def hunt(self):
        print("hunting") 
```

## Further Reading

* [Pylint - E0211](http://pylint-messages.wikidot.com/messages:e0211)
