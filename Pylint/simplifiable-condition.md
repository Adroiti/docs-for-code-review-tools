Pattern: Complex boolean condition

Issue: -

## Description

Emitted when a boolean condition is able to be simplified.

Example of **incorrect** code:

```python
bool(CONSTANT or True)  # [simplifiable-condition]
```

Example of **correct** code:

```python
CONSTANT or True
```
