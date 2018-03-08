Pattern: Use of deprecated function on `itertools` module

Issue: -

## Description

Emitted when accessing a function on `itertools` that has been removed in Python 3. Use `six.moves` to import a Python 2 and Python 3 compatible function instead.

Example of **incorrect** code:

```python
from itertools import izip
print(list(izip([1, 2], [3])))
```

Example of **correct** code:

```python
from six.moves import zip
print(list(zip([1, 2], [3])))
```
