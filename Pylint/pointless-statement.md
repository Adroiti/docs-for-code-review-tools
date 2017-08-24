Pattern: Pointless statement

Issue: -

## Description

Used when a statement doesn't have (or at least seems to) any effect. This may lead to confusion by readers, side effects and increased code size. Update or remove such code to resolve this issue.


Example of **incorrect** code:

```python
def test_method():
    __revision__ <= 1  # [pointless-statement]
    return "42"
```

Example of **correct** code:

```python
def test_method():
    return "42"
```

## Further Reading

* [Pylint - W0104](http://pylint-messages.wikidot.com/messages:w0104)
