Pattern: Use of non-lazy logging

Issue: -

## Description

Used when a logging statement has a call form of `logging.<logging method>(format_string % (format_args...))`. Such calls should leave string interpolation to the logging method itself so that the program may avoid incurring the cost of the interpolation in those cases in which no message will be logged.


Example of **incorrect** code:

```python
logging.warn('%s, %s' % (1, 2))
```

Example of **correct** code:

```python
logging.warn('%s, %s', 1, 2)
```

## Further Reading

* [PEP 282 - A Logging System](http://www.python.org/dev/peps/pep-0282)
