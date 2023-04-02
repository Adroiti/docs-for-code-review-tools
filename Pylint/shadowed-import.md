Pattern: Use of shadowed import

Issue: -

## Description

Used when a module is aliased with a name that shadows another import.

Example of **incorrect** code:

```python
from pathlib import Path

import FastAPI.Path as Path  # [shadowed-import]
```

Example of **correct** code:

```python
from pathlib import Path

import FastAPI.Path as FastApiPath
```

