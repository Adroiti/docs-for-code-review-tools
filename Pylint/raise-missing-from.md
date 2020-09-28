Pattern: Missing use of `raise from`

Issue: -

## Description

Python 3's exception chaining means it shows the traceback of the current exception, but also the original exception. Not using `raise from` makes the traceback inaccurate, because the message implies there is a bug in the exception-handling code itself, which is a separate situation than wrapping an exception.

Example of **incorrect** code:

```python
try:
    1 / 0
except ZeroDivisionError:
    # +1: [raise-missing-from]
    raise KeyError
```

Example of **correct** code:

```python
try:
    1 / 0
except ZeroDivisionError:
    raise KeyError from foo
```