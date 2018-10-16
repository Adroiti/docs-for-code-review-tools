Pattern: Useless import alias

Issue: -

## Description

Used when an import alias is same as original package.

Example of **incorrect** code:

```python
import numpy as numpy
```

Example of **correct** code:

```python
import numpy as np
```
