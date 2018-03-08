Pattern: Abstract method is not overridden

Issue: -

## Description

If a method is designed as abstract in a parent class and the child class does not implement the method, then Python will raise a `TypeError` error at runtime if you attempt to instantiate any object that contains abstract methods. Update parent class or implement abstract method to resolve this issue.

Example of **incorrect** code:

```python
import abc

class Felinae(object):
    __metaclass__ = abc.ABCMeta

    def __init__(self, name):
        self.name = name

    @abc.abstractmethod
    def hunt(self):
        return

class Puma(Felinae):
    def __init__(self, name):
        super(Puma, self).__init__(name, name)

# TypeError: can't instantiate abstract class
s = Puma("Mountain lion")
```

Example of **correct** code:

```python
import abc

class Felinae(object):
    __metaclass__ = abc.ABCMeta

    def __init__(self, name):
        self.name = name

    @abc.abstractmethod
    def hunt(self):
        return

class Puma(Felinae):
    def __init__(self, name):
        super(Puma, self).__init__(name, name)
    def hunt(self):
        print("hunting")    

s = Puma("Mountain lion")
```

## Further Reading

* [Pylint - W0223](http://pylint-messages.wikidot.com/messages:w0223)
