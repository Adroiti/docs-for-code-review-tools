Pattern: Prefer separate lines over single line for imports

Issue: -

## Description

This rule enforces PEP 8 style guide recommendation to prefer separate lines for imports over a single line.


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
