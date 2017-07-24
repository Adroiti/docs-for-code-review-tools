Pattern: Use of non-lazy format logging

Issue: -

## Description

Used when a logging statement has a call form of `logging.<logging method>(format_string.format(format_args...))`. Such calls should use `%` formatting instead, but leave interpolation to the logging function by passing the parameters as arguments.


Example of **incorrect** code:

```python
logging.warn('{0}, {1}'.format(1, 2))
```

Example of **correct** code:

```python
logging.warn('%s, %s', 1, 2)
```

## Further Reading

* [PEP 282 - A Logging System](http://www.python.org/dev/peps/pep-0282)
