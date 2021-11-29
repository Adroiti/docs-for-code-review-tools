Pattern: Overridden `typing.final` method

Issue: -

## Description

Used when a method decorated with `typing.final` has been overridden.


Example of **incorrect** code:

```python
from typing import final

class Base:
    @final
    def my_method(self):
        pass


class Subclass(Base):
    def my_method(self): # [overridden-final-method]
        pass

```

Example of **correct** code:

```python
from typing import final

class Base:
    def my_method(self):
        pass


class Subclass(Base):
    def my_method(self):
        pass
```
