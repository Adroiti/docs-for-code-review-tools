Pattern: Trailing newline

Issue: -

## Description

Used when there are trailing blank lines in a file.


Example of **incorrect** code:

```python
"""This file has trailing newlines."""
print "test"
# +1: [trailing-newlines]
 
 


```

Example of **correct** code:
```python
print "test"
# +1: [trailing-newlines]
```
