Pattern: Use of f-string without interpolation

Issue: -

## Description

This check is emitted whenever Pylint detects the use of an f-string without having any interpolated values in it, which means that the f-string can be a normal string.

Example of **incorrect** code:

```python
print(f"ERROR")
```

Example of **correct** code:

```python
import math

VALUE = 1

print(f"some value {VALUE}")
print(f'pi: {math.pi:.3f}')
```