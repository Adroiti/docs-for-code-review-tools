Pattern: Use of invalid type when raising exception

Issue: -

## Description

A `raise` statement must raise a valid exception type, otherwise Python raises a `TypeError` at runtime.


Example of **incorrect** code:

```python
def bad_case():
    raise 1  # [raising-bad-type]

```

Example of **correct** code:

```python
def good_case():
    raise ValidException('error details')
```

## Further Reading

* [Pylint - E0702](http://pylint-messages.wikidot.com/messages:e0702)
