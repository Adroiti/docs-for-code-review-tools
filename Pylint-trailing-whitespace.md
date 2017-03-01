Pattern: Remove trailing whitespace

Issue: -

## Description

This rule enforces `PEP 8` recommendation to avoid trailing whitespace anywhere. Because it's usually invisible, it can be confusing: e.g. a backslash followed by a space and a newline does not count as a line continuation marker. Some editors don't preserve it and many projects (like _CPython_ itself) have pre-commit hooks that reject it.


Example of **incorrect** code:
```python
print('some trailing whitespace after this statement')   
```

Example of **correct** code:
```python
print('no trailing whitespace')
```

## Further Reading

* [Pylint - Other Recommendations](https://www.python.org/dev/peps/pep-0008/#other-recommendations)
* [Pylint - C0303](http://pylint-messages.wikidot.com/messages:c0303)
