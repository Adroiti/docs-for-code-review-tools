Pattern: Call `__init__` related to direct ancestor

Issue: -

## Description

Used when an `__init__` method is called on a class which is not in the direct ancestors for the analysed class. This may lead to confusion by readers. Review the class in question to make sure this functionality is intended.


Example of **incorrect** code:

```python
class Felinae(object):
    def __init__(self, subfamily):
        self.subfamily = subfamily

# if Puma was a descendant this would be "class Puma(Felinae):"
class Puma(object):
    def __init__(self, subfamily, genus):
        self.genus = genus
        Felinae.__init__(self, subfamily)  # calling __init__ of non-direct base class
```

Example of **correct** code:

```python
class Felinae(object):
    def __init__(self, subfamily):
        self.subfamily = subfamily

# Puma is now a descendant of Felinae
class Puma(Felinae):
    def __init__(self, subfamily, genus):
        self.genus = genus
        Felinae.__init__(self, subfamily)  # calling __init__ of non-direct base class
```

## Further Reading

* [Pylint - W0233](http://pylint-messages.wikidot.com/messages:w0233)
