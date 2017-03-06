Pattern: Variable accessed before assignment

Issue: -

## Description

If variable is used before assignment, a runtime error will be raised. Assign it first to resolve this issue.


Example of **incorrect** code:

```python
print(name)
name = "test"
```

Example of **correct** code:

```python
name = "test"
print(name)
```

## Further Reading

* [Pylint - E0601](http://pylint-messages.wikidot.com/messages:e0601)
