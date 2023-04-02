Pattern: Unnecessary exception statement

Issue: -

## Description

Used when an exception is created without being assigned, raised or returned for subsequent use elsewhere.

Example of **incorrect** code:

```python
Exception("This exception is a statement.")  # [pointless-exception-statement]
```

Example of **correct** code:

```python
raise Exception("This will raise.")
```
