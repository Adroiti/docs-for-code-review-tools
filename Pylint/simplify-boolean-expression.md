Pattern: Missing use of simple boolean expression

Issue: -

## Description

Emitted when redundant pre-python 2.5 ternary syntax is used.


Example of **incorrect** code:

```python
value = condition and False or other_value
```

Example of **correct** code:

```python
value = other_value
```

