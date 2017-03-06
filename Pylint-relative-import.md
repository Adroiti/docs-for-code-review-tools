Pattern: Prefer absolute over relative imports

Issue: -

## Description

This rule enforces _PEP 8_ style guide recommendation to use absolute over relative imports. They are usually more readable and tend to be better behaved (or at least give better error messages) if the import system is incorrectly configured (such as when a directory inside a package ends up on `sys.path`):


```python
import mypkg.sibling
from mypkg import sibling
from mypkg.sibling import example
```

However, explicit relative imports are an acceptable alternative to absolute imports, especially when dealing with complex package layouts where using absolute imports would be unnecessarily verbose:


```python
from . import sibling
from .sibling import example
```

Standard library code should avoid complex package layouts and always use absolute imports.

## Further Reading

* [PEP 8 - Imports](https://www.python.org/dev/peps/pep-0008/#imports)
