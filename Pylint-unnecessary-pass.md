Pattern: Avoid unnecessary `pass` statements

Issue: -

## Description

A `pass` statement is only necessary when it is the only statement in a block. If the block already contains other statements then the pass statement is unnecessary and can be removed.


Example of **incorrect** code:

```python
try:
    A = 1
except ValueError:
    A = 2
    pass # [unnecessary-pass]
```

Example of **correct** code:

```python
try:
    A = 1
except ValueError:
    pass
```

## Further Reading

* [The Python Tutorial - pass Statements](https://docs.python.org/2/tutorial/controlflow.html#pass-statements)
* [Pylint - W0107](http://pylint-messages.wikidot.com/messages:w0107)
