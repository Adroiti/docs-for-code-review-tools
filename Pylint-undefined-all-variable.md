Pattern: Undefined name in `__all__`

Issue: -

## Description

Used when an undefined variable name is referenced in `__all__`. Python raises a `ImportError` whenever another module attempts to use this undefined object.


Example of **incorrect** code:

```python
# NonExistant is listed in __all__ but is not defined in this module. An error is expected.
from os import path
from collections import deque

__all__ = ['deque', 'NonExistant', 'path']  # [undefined-all-variable]
```

Example of **correct** code:

```python
from os import path
from collections import deque

__all__ = ['deque', 'path']
```

