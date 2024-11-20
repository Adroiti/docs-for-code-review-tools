Pattern: Unnecessary negation

Issue: -

## Description

Used when a boolean expression contains an unneeded negation, e.g. when two negation operators cancel each other out.

Example of **incorrect** code:

```python
if not not input():  # [unnecessary-negation]
    pass
```

Example of **correct** code:

```python
if input():
    pass
```
