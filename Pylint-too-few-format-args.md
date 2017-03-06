Pattern: Too few format args

Issue: -

## Description

Calls to `format()` that do not match formats against args may lead to confusion as code will not work as expected. Extra arguments will not be shown and missings arguments will raise `IndexError`. Update code so that formats and args are in sync.


Example of **incorrect** code:

```python
"{0} {1} {2}".format(1, 2) # [too-few-format-args]
```

Example of **correct** code:

```python
"{0} {1} {2}".format(1, 2, 3)
```

## Further Reading

* [The Python Standard Library - format()](https://docs.python.org/2/library/functions.html#format)
* [Pylint - E1306](http://pylint-messages.wikidot.com/messages:e1306)
