Pattern: Fixme

Issue: -

## Description

Used as a warning note when `FIXME` or `XXX` is detected.


Example code that will generate this issue:

```python
# FIXME: Seems like this loop should be finite.
while True: ...
```

Resolved code:

```python
while True: ...
```

If you are into Extreme Programming, it would make more sense to place all the `FIXME`'s and `TODO`'s in corresponding functional test suites. That way you can never forget about them, and the feedback about project progress will be more complete and more accurate. 
