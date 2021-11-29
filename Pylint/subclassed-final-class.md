Pattern: Subclassed `typing.final` class

Issue: -

## Description

Used when a class decorated with `typing.final` has been subclassed.


Example of **incorrect** code:

```python
from typing import final

@final
class Base:
    pass

class Subclass(Base): # [subclassed-final-class]
    pass
```

Example of **correct** code:

```python
from typing import final

class Base:
    pass

class Subclass(Base): # [subclassed-final-class]
    pass
```
