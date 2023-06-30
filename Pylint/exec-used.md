Pattern: Use of `exec()`

Issue: -

## Description

The `exec()` statement is dangerous, hard to test, and hard to read. Avoid it, as much as possible. This is largely due to the fact that `exec()` enables you to dynamically execute arbitrary Python code which is stored in literal strings. Consider going back to the code to check if there is a clearer, more direct way to accomplish the task.


Example of **incorrect** code:

```python
text = "print \"hello, and goodbye\""
exec text
```

Example of **correct** code:

```python
def foo():
    print "hello, and goodbye"
    
foo()
```

## Further Reading

* [The Python Standard Library - exec()](https://docs.python.org/3/library/functions.html#exec)
