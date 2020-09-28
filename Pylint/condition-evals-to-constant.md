Pattern: Condition evals to constant

Issue: -

## Description

Emitted when a boolean condition can be simplified to a constant value.
 
Example of **incorrect** code:

```python
bool(CONSTANT or True)  # [condition-evals-to-constant]
```

Example of **correct** code:

```python
CONSTANT or True
```
