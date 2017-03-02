Pattern: Too many logging args

Issue: -

## Description

Calls to logging that do not match formats against args may lead to confusion as code will not work as expected. Extra arguments will not be shown and missings arguments will raise `IndexError`. Update code so that formats and args are in sync.


Example of **incorrect** code:

```python
logging.warn('%s, %s', 1, 2, 3)
```

Example of **correct** code:

```python
logging.warn('%s, %s', 1, 2)
```

## Further Reading

* [PEP 282 - A Logging System](http://www.python.org/dev/peps/pep-0282)
