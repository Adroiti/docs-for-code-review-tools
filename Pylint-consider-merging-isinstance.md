Pattern: Consider merging `isinstance()` calls

Issue: -

## Description

Used when multiple consecutive `isinstance()` calls can be merged into one.


Example of **incorrect** code:

```python
    var = range(10)

    if isinstance(var[1], (int, float)):
        print ("is int or float")
```

Example of **correct** code:

```python
    var = range(10)

    if isinstance(var[1], int) or isinstance(var[1], float):
        print ("is int or float")
```
