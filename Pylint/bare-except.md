Pattern: Use of bare `except`

Issue: -

## Description

Used when an except clause doesn't specify exceptions type to catch. 


Catching exceptions should be as precise as possible. Using a catch-all `Exception` instance defeats the purpose of knowing the type of error that occurred, and prohibits the use of tailored responses. By not specifying an exception type, you might also loose information about the error itself.


Example of **incorrect** code:

```python
def division(dividend, divisor):
    try:
      result = dividend / divisor
    except:
      result = None

  return result
```

Example of **correct** code:

```python
def division(dividend, divisor):
    result = None

    try:
        result = dividend / divisor
    except ZeroDivisionError:
        print "Division by 0."
    except TypeError:
        print "Type error: division by '{0}'.".format(divisor)
    except Exception as e:
        print "Error '{0}' occurred. Arguments {1}.".format(e.message, e.args)
    finally:
        if result is None:
            result = 0

    return result
```

## Further Reading

* [PEP 8 - Programming Recommendations](https://www.python.org/dev/peps/pep-0008/#programming-recommendations)
* [The Python Tutorial » Errors and Exceptions](https://docs.python.org/2/tutorial/errors.html)
