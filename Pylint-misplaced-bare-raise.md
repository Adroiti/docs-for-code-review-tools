Pattern: Misplaced bare `raise`

Issue: -

## Description

Used when a bare `raise` is not inside an `except` clause. This generates an error, since there are no active exceptions to be reraised. 


An exception to this rule is represented by a bare `raise` inside a `finally` clause, which might work, as long as an exception is raised inside the `try` block, but it is nevertheless a code smell that must not be relied upon.


Example of **incorrect** code:

```python
try:
    raise # outside of except clause
except Exception:
    print("error details")
```

Example of **correct** code:

```python
try:
    pass
except Exception:
    print("error details")
    raise
```

## Further Reading

* [The Python Tutorial - Errors and Exceptions](https://docs.python.org/2/tutorial/errors.html)
