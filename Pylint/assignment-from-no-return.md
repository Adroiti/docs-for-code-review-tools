Pattern: Assigning to function call which doesn't return

Issue: -

## Description

Used when an assignment is done on a function call but the inferred function doesn't return anything. This may be confusing to readers and should be updated so that function is returning or callers do not assign result.


Example of **incorrect** code:

```python
def do_stuff():
    print('no return')


def func():
    result = do_stuff()  # result is always None
    print(result)
```

Example of **correct** code:

```python
def do_stuff():
    return "details"


def func():
    result = do_stuff()
    print(result)
```
