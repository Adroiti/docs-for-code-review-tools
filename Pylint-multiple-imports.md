Pattern: Use of single line instead of separate lines for imports

Issue: -

## Description

This rule enforces _PEP 8_ style guide recommendation to prefer separate lines for imports over a single line.


Example of **incorrect** code:

```python
import os, socket
```

Example of **correct** code:

```python
import os
import socket
```

## Further Reading

* [PEP 8 - Imports](https://www.python.org/dev/peps/pep-0008/#imports)
