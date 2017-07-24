Pattern: `super()` not using child class name as first argument

Issue: -

## Description

The first argument to `super()` should be the name of the current child class calling `super()`. If a valid child class name is not provided Python will raise a `TypeError` at runtime.


Example of **incorrect** code:

```python
class Felinae(object):
    def __init__(self, name):
        self.name = name

class Puma(Felinae):
    def __init__(self, name):
        # bad first argument to super()
        super(self, Puma).__init__(name) 
```

Example of **correct** code:

```python
class Felinae(object):
    def __init__(self, name):
        self.name = name

class Puma(Felinae):
    def __init__(self, name):
        super(Puma, self).__init__(name) 
```

## Further Reading

* [Python Standard Library - super()](https://docs.python.org/2/library/functions.html#super)
* [Pylint - E1003](http://pylint-messages.wikidot.com/messages:e1003)
