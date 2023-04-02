Pattern: Use of implicit flag alias

Issue: -

## Description

Used when multiple integer values declared within an `enum.IntFlag` class share a common bit position.

Example of **incorrect** code:

```python
from enum import IntFlag


class FilePermissions(IntFlag):
    READ = 1
    WRITE = 2
    EXECUTE = 3  # [implicit-flag-alias]
```

Example of **correct** code:

```python
from enum import IntFlag


class FilePermissions(IntFlag):
    READ = 1
    WRITE = 2
    EXECUTE = 4
```