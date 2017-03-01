Pattern: Avoid trailing newlines

Issue: -

## Description

Used when there are trailing blank lines in a file.


Example of **incorrect** code:

```python
"""This file has 2 trailing newlines."""
print "test"
# +1: [trailing-newlines]


```

Example of **correct** code:
```python
print "test"
# +1: [trailing-newlines]
```
