Pattern: Use of named expression without context

Issue: -

## Description

Emitted if named expression is used to do a regular assignment outside a context like if, for, while, or a comprehension.

Example of **incorrect** code:

```python
(a := 42)  # [named-expr-without-context]
```

Example of **correct** code:

```python
if (a := 42):
    print('Success')
```