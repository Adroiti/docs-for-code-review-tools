Pattern: Logging unsupported format

Issue: -

## Description

Calls to logging that contain unsupported format character will raise `ValueError` at runtime. Update code so that all format character are valid.


Example of **incorrect** code:

```python
logging.warn('Hello%20World%s', "!")
```

Example of **correct** code:

```python
logging.warn('Hello%%20World%s', "!") # escaped %20
```

## Further Reading

* [PEP 282 - A Logging System](http://www.python.org/dev/peps/pep-0282)
