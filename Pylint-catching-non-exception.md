Pattern: Inherit from `Exception` for all custom exceptions

Issue: -

## Description

All built-in, non-system-exiting exceptions are derived from `Exception`. All user-defined exceptions should also be derived from this class. 


Example of **incorrect** code:

```python
# Does not inherit from Exception
class CustomException(object):
    pass
    
try:
    1 + 1
except CustomException:
    print("caught")
```

Example of **correct** code:

```python
class CustomException(Exception):
    pass
    
try:
    1 + 1
except CustomException:
    print("caught")
```

## Further Reading

* [The Python Standard Library - Built-in Exceptions](https://docs.python.org/2/library/exceptions.html)
