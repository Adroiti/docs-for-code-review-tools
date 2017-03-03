Pattern: Avoid accessing protected class members from outside

Issue: -

## Description

This rule enforces object-oriented programming principle to disallow direct access to protected members. Use property to access the member or add protected member to `__all__` to resolve this issue.


Example of **incorrect** code:

```python
class Felinae(object):
    def __init__(self, genus):
        self._genus = genus

cat = Felinae("Puma")
# direct access of protected member
print "Name: %s".format(cat._genus)
```

Example of **correct** code:


```python
class Felinae(object):
    def __init__(self, genus):
        self._genus = genus
        
    @property
    def genus(self):
        return self._genus        

cat = Felinae("Puma")
print "Name: %s".format(cat.genus)
```

## Further Reading

* [Wikipedia - Object-oriented programming - Encapsulation](https://en.wikipedia.org/wiki/Object-oriented_programming#Encapsulation)
* [Pylint - W0212](http://pylint-messages.wikidot.com/messages:w0212)
