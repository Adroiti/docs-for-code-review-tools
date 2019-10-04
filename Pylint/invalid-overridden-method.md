Pattern: Invalid overridden method

Issue: -

## Description

Used when we detect that a method was overridden as a property or the other way around, which could result in potential bugs at runtime.

Example of **incorrect** code:

```python
class SuperClass(metaclass=abc.ABCMeta):
    @property
    @abc.abstractmethod
    def prop(self):
        pass

    @abc.abstractmethod
    def method(self):
        pass


class NoProp(SuperClass):
    def prop(self):  # [invalid-overridden-method]
        return None

    @property
    def method(self): # [invalid-overridden-method]
        return None
```

Example of **correct** code:

```python
class SuperClass(metaclass=abc.ABCMeta):
    @property
    @abc.abstractmethod
    def prop(self):
        pass

    @abc.abstractmethod
    def method(self):
        pass


class Prop(SuperClass):
    @property
    def prop(self):
        return None

    def method(self):
        pass
```