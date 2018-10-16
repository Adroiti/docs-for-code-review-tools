Pattern: Missing use of chained comparison

Issue: -

## Description

Emitted if a boolean operation can be simplified by chaining some of its operations.

Example of **incorrect** code:

```python
a < b and b < c
```

Example of **correct** code:

```python
a < b < c
```