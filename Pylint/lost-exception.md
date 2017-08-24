Pattern: Lost exception

Issue: -

## Description

Used when a `break` or a `return` statement is found inside the `finally` clause of a `try...finally` block: the exceptions raised in the `try` clause will be silently swallowed instead of being re-raised.


Example of **incorrect** code:

```python
def do_stuff():
	try:
		result = 1/0
	finally:
		break
```

Example of **correct** code:

```python
def do_stuff():
	try:
		result = 1/0
	finally:
		print "done"
```

## Further Reading

* [The Python Tutorial - Tuples and Sequences](https://docs.python.org/2/tutorial/datastructures.html#tuples-and-sequences)
