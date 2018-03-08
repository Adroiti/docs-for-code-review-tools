Pattern: Use of deprecated field on `types` module

Issue: -

## Description

Emitted when accessing a field on `types` that has been removed in Python 3. Use the declarations in the `builtin` namespace instead.

Example of **incorrect** code:

```python
from types import ListType
print(isinstance([], ListType))
```

Example of **correct** code:

```python
print(isinstance([], list))
```
