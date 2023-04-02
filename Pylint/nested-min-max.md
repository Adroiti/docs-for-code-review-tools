Pattern: Use of nested `min`/`max`

Issue: -

## Description

Nested calls `min(1, min(2, 3))` can be rewritten as `min(1, 2, 3)`.

Example of **incorrect** code:

```python
print(min(1, min(2, 3)))  # [nested-min-max]
```

Example of **correct** code:

```python
print(min(1, 2, 3))
```
