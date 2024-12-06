Pattern: Context used in function will not be exited

Issue: -

## Description

Used when a contextmanager is used inside a generator function and the cleanup is not handled.

Examples:

```python
import contextlib


@contextlib.contextmanager
def cm():
    contextvar = "acquired context"
    print("cm enter")
    yield contextvar
    print("cm exit")


def genfunc_with_cm():
    with cm() as context:  # [contextmanager-generator-missing-cleanup]
        yield context * 2
```
