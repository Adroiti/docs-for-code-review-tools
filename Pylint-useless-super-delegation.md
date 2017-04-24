Pattern: Useless super delegation in method

Issue: -

## Description

Used when overridden method is useless, relying on `super()` delegation to do the same thing as another method from the MRO.


Example of **incorrect** code:

```python
class Base(object):

    def something(self):
        pass
        
        
class UselessSuper(Base):

    def equivalent_params(self): # [useless-super-delegation]
        return super(UselessSuper, self).equivalent_params()
```

Example of **correct** code:

```python
class Base(object):

    def something(self):
        pass
        
def trigger_something(value_to_trigger):
    pass
    
    
class NotUselessSuperDecorators(Base):
    @trigger_something('value1')
    def method_decorated(self):
        super(NotUselessSuperDecorators, self).method_decorated()
```

## Further Reading

* [Related link(s) to get more details or background on issue pattern](https://www.python.org)
