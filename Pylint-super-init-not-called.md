Pattern: Call `__init__` method from base class

Issue: -

## Description

Derived class should always call it's parent's `__init__` method if available. Otherwise this could lead to partially initialized instance state causing unexpected behvarior.


Example of **incorrect** code:

```python
class Felinae(object):
    def __init__(self, subfamily):
        self.subfamily = subfamily

class Puma(Felinae):
    def __init__(self, subfamily, genus):
        self.genus = genus
```

Example of **correct** code:

```python
class Felinae(object):
    def __init__(self, subfamily):
        self.subfamily = subfamily

class Puma(Felinae):
    def __init__(self, subfamily, genus):
        super(Puma, self).__init__(subfamily)
        self.genus = genus
```

## Further Reading

* [Pylint - W0231](http://pylint-messages.wikidot.com/messages:w0231)
