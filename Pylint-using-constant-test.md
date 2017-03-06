Pattern: Avoid using constant in test

Issue: -

## Description

Emitted when a conditional statement uses a constant value for its test. This might not be what the user intended to do. Review such code to resolve this issue.


Example of **incorrect** code:
```python
if 2.0: # [using-constant-test]
    print "found 2.0"
```

Example of **correct** code:
```python
number = 1.0

if (number == 2.0):
    print "found 2.0"
```
