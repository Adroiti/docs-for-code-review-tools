Pattern: Unmerged `isinstance()` call

Issue: -

## Description

Used when multiple consecutive `isinstance()` calls can be merged into one thus improving code readability.


Example of **incorrect** code:

```python
var = range(10)

if isinstance(var[1], int) or isinstance(var[1], float):
    print ("is int or float")
```

Example of **correct** code:

```python
var = range(10)

if isinstance(var[1], (int, float)):
    print ("is int or float")
```
