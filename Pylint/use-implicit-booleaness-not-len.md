Pattern: Use of `len(sequence)` as condition value

Issue: -

## Description

Used when incorrect use of `len(sequence)` is detected inside conditions. Use `if sequence` or `if not sequence` instead.


Example of **incorrect** code:

```python
if len(args):
    pass

if not len(args):
    pass
```

Example of **correct** code:

```python
if args:
    pass

if not args:
    pass
```
