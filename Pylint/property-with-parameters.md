Pattern: Use of property with parameters

Issue: -

## Description

Used when we detect that a property also has parameters, which are useless, given that properties cannot be called with additional arguments.

Example of **incorrect** code:

```python
class Cls:
    @property
    def attribute(self, param, param1): # [property-with-parameters]
        return param + param1
```

Example of **correct** code:

```python
class Cls:
    @property
    def attribute(self):
        return self.test
```
