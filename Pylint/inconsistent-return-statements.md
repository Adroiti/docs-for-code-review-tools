Pattern: Inconsistent return statement

Issue: -

## Description

Be consistent in return statements. Either all return statements in a function should return an expression, or none of them should. If any return statement returns an expression, any return statements where no value is returned should explicitly state this as return `None`, and an explicit return statement should be present at the end of the function (if reachable).

Example of **incorrect** code:
```python
def mix_implicit_explicit_returns(arg):
	if arg < 10:
		return True
	elif arg < 20:
		return
```

Example of **correct** code:
```python
def mix_implicit_explicit_returns(arg):
	if arg < 10:
		return True
	elif arg < 20:
		return None
```

## Further Reading

* [PEP 8 — the Style Guide for Python Code](http://pep8.org/#programming-recommendations)